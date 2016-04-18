选择器命名(参考BEM规范)
------------

###避免使用###

除特殊情况，应尽量避免使用id选择器。

除了reset中，应尽量少使用标签选择器，避免污染。

###层级内命名###

1、应使用有意义的英文单词或者缩写，可以使用一些约定俗成的非规范缩写；

2、如使用拼音，必须使用全拼，不得简写； 如名称为词组，以驼峰形式书写；

3、名称可为1级或多层组成，最多不超过3级，多层级命名使用连字符（中横线）连接；

###名词与通用规范###

**模块：**

.moduleName-subName ；
 
逻辑上和功能上相互独立的可复用的组成部分；
 
模块可在布局上嵌套于另一模块但无逻辑从属关系；
 
**页面：** 

以page-为前缀；

页面可看作一种特俗模块；

**元素：**

 .moduleName-subName__elemName-subName (模块名__元素名)；
 
 元素指从属于某模块的组成部分，不能脱离模块使用；
 
 模块名与元素名之间以2条下划线分隔；
 
**状态：**

 .is-status ；
 
 以is-为前缀；
 
 用来定义模块或者元素在不同状态下的展现样式；

**位置：**

 .in-position;  
 .in-page;  
 .in-parentModule;

  定义模块或者元素在位于某个特定位置、从属于某个页面或者某个父模块时的特定展现样式；
 
**动态添加：**

 js脚本处理中动态添加的未预定义的class，在可控的场景下，以js-为前缀；
 
**举例：**

    .page-index {...}  
    .popbox-userInfo {...}  
    .popbox-userInfo.is-hidden {...}  
    .popbox-userInfo__btn-submit {...}  
    .popbox-userInfo__btn-submit.is-disabled {...}
    .popbox-userInfo__btn-submit.in-page-help {...}


###公用组件定义###

如按钮、表单控件等，可预先定义样式；

需要在模块内覆盖默认样式的，可加上独立的命名（使用规范命名方式，不可.name.in-parentModule方式）；

应用时，应先引入公用组件名，再使用自身独立命名；

**举例：**

    .btn {...}  
    .btn-big {...}   
    .btn-small {...}   
    .btn-blue {...}  
    .btn-red {...}  
    ...  
    .popbox-userInfo__btn-submit {...}  
    .popbox-userInfo__btn-submit.is-disabled {...}  
    ...  
    `<div class="btn btn-big btn-blue popbox-userInfo__btn-submit is-disabled">`
