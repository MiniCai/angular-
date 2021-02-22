# angular-
重点概括

一、基础语法用法

(): 绑定方法   
eg: (click)="a($event)"

[]、{{}}: 单向绑定值 
eg: [attr.xxx] 、[class.xxx] 、 [style.xxx.单位] 、 [test]="change" 、 {{employer?.companyName}} (?表示可选)

[()]: 双向绑定（表单 [(ngModel)] ：import { FormsModule } from '@angular/forms'; ）   
eg: <my-cmp [(title)]="name">  <=>  <my-cmp [title]="name" (titleChange)="name=$event">

#xxx : 能获取到dom   
eg: <video #movieplayer><button (click)="movieplayer.play()"></video>

*xxx : 把当前元素转换成一个内嵌的模板，除指令(eg:*ngIf)外
eg: <p *myUnless="myExpression"></p>  <=> <ng-template [myUnless]="myExpression"><p>...</p></ng-template>

| : 管道: 用于格式化字段，angular 提供一系列管道（内置过滤器），可先查询，没有才自己写  
https://angular.cn/api?type=pipe
{
    AsyncPipe: async —— 从一个异步回执中解出一个值, 
    CurrencyPipe: currency —— 货币,
    DatePipe: date —— 日期格式化,
    DecimalPipe: number —— 把数字转换成字符串,
    I18nPluralPipe: pluralMap —— 将值映射到根据语言环境规则对值进行复数的字符串,
    I18nSelectPipe: i18nSelect —— 通用选择器，显示与当前值匹配的字符串,
    JsonPipe: json —— 格式化json对象,
    KeyValuePipe: keyvalue —— 将Object或Map转换为键值对数组,
    LowerCasePipe: lowercase —— 小写,
    UpperCasePipe: uppercase —— 大写,
    PercentPipe: percent —— 把数字转换成百分比字符串,
    SlicePipe: slice —— 从一个 Array 或 String 中创建其元素一个新子集（slice）,
    TitleCasePipe: titlecase —— 文本转换成标题形式, 通常为英文标题需要
}
eg: {{ a | b }}
 


二、模板指令（内置指令）（import { CommonModule } from '@angular/common';）
https://angular.cn/guide/ajs-quick-reference#template-directives

1、结构型指令: 可以操纵HTML的元素布局，*表示(语法糖, 可解开语法糖，变成 <ng-template> 的形式)
https://angular.cn/guide/structural-directives
*ngIf
*ngFor="let item of list"
[ngSwitch](属性型指令) + *ngSwitchCase + *ngSwitchDefault(值为undefined) <=>（js中switch语句）

2、属性型指令: 某些属性型指令可无[], eg: <p appHighlight>Highlight me!</p> 或者 <a [href]=""></a>
[ngClass]
[ngStyle]
[hidden]: 隐藏或显示一个元素
[href]: <a [href]=""></a>
[routerLink]: <a [routerLink]="['/..']"></a>
[src]
[...]

3、
<ng-container> 是一个由 Angular 解析器负责识别处理的语法元素。 它不是一个指令、组件、类或接口，更像是 JavaScript 中 if 块中的花括号。

<ng-template>是一个 Angular 元素，用来渲染 HTML。 它永远不会直接显示出来。 事实上，在渲染视图之前，Angular 会把 <ng-template> 及其内容替换为一个注释。
如果没有使用结构型指令，而仅仅把一些别的元素包装进 <ng-template> 中，那些元素就是不可见的。



三、 ts 撰写顺序
(可按照字母顺序排列）
按分类: 属性 => 方法
按范围: 公共 => 私有


四、 通信
1、路由参数
2、@Input @Output
3、
  


五、Angular CLI 命令自动生成模板文件 (生成指定的 module / component / directive / pipe /service 等等.. )
https://angular.cn/cli/generate#component-command
eg: ng generate module xxx    ===  ng g m xxx



六、路由
https://angular.cn/api/router





< ---------------------- ********************************** ---------------------- >
更多案例：

<div title="Hello {{ponyName}}"> <=> <div [title]="'Hello ' + ponyName">

<svg:rect x="0" y="0" width="100" height="100"/>  <=>  <svg><rect x="0" y="0" width="100" height="100"/></svg>
