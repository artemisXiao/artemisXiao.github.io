### Template7 封装渲染方法
···
/**
 * Created by Administrator on 2018/1/30.
 */

/**
 * 动态模板加载
 * 依赖
 * jquery  template7
 * @type {{}}
 */

TPL = function (param) {
    if (!param.url) {
        console.error("TPL param object not config tpl {url}");
        return;
    }
    if (!param.elem) {
        console.error("TPL param object not config tpl {elem}");
        return;
    }
    if (!param.context) {
        console.error("TPL param object not config tpl {context}");
        return;
    }
    var obj = typeof param.elem == "object" ? param.elem : $(param.elem);
    var success = function (template) {
        param.template = template;
        var compiledTemplate = Template7.compile(param.template);
        param.html = compiledTemplate(param.context);
        if (param.before) {
            param = param.before(param);
        }
        if (param.append) {
            console.info("TPL append template to document");
            obj.append(param.html);
        } else {
            console.info("TPL html template to document");
            obj.html(param.html);
        }
        if (param.after) {
            param.after(param);
        }
    };
    var template = session_Storage_.get(encodeURI(param.url));
    if (template && 0) {
        success(template);
    } else {
        $.get(
            param.url,
            function (template) {
                session_Storage_.set(encodeURI(param.url), template);
                success(template);
            }
        );
    }
};
$.extend({
    tpl: TPL
});

//使用  
$.tpl(options);
···