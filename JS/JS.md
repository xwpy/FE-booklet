# JS知识结构

　　如果某些事情就像魔法一样，那意味着看到了新生事物的曙光，任何足够先进的技术都和魔法无异。

　　javascript就如同魔法一样，它是一门充满活力、简单易用的语言，又是一门具有许多复杂微妙技术的语言。即使是经验丰富的javascript开发者，如果没有认真学习的话，也无法真正理解它们，这就是javascript的矛盾之处。由于javascript不必理解就可以使用，因此通常来说很难真正理解语言本身，这就是我们面临的挑战。不满足于只是让代码正常工作，而是想要弄清楚为什么，勇于挑战这条崎岖颠簸的少有人走的路，拥抱整个javascript

　　纷繁复杂的库，大多都以javascript为基础。实际上，前端工程师很大程度上指javascript工程师。前端入门容易精通难，说的是前端，更指的是javascript。如果把掌握HTML和CSS作为进入”前端大学“的高中知识贮备，那么javascript就是”前端大学“的主修课程，如何在”毕业“后成功开启自己的前端人生，要看javascript知识学得深不深，理解得透彻不透彻，所以在javascript上投入多少时间都不为过

　　小火柴将javascript的知识体系进行了梳理和归纳，总结成以下目录

  * ECMAScript
      1. 基础语法
          * 基础
            * [词法结构](ECMA/baseGrammer/LexicalStructure.md)
            * [变量和标识符](ECMA/baseGrammer/variable.md)
            * [属性和变量](ECMA/baseGrammer/attr.md)
            * [表达式](ECMA/baseGrammer/expression.md)
            * [严格模式](ECMA/baseGrammer/strict.md)
            * [垃圾收集机制](ECMA/baseGrammer/garbageCollection.md)
            * [动态脚本](ECMA/baseGrammer/dynamicScript.md) 
          * 运算符
            * [运算符语法概述](ECMA/baseGrammer/operatorOverview.md)     
            * [算术运算符](ECMA/baseGrammer/arithmeticOperator.md)
            * [关系运算符](ECMA/baseGrammer/RelationalOperator.md)
            * [逻辑运算符](ECMA/baseGrammer/logicalOperator.md)
            * [位运算符](ECMA/baseGrammer/bit.md)
            * [条件、逗号、赋值、()和void运算符](ECMA/baseGrammer/otherOperator.md) 
          * 语句
            * [表达式语句、块语句、空语句和声明语句](ECMA/baseGrammer/statementsAndEmptyAndBlockAndDeclarationStatement.md) 
            * [条件语句、循环语句和跳转语句](ECMA/baseGrammer/conditionalsAndLoopsAndJumps.md) 
            * [eval和with](ECMA/baseGrammer/evalAndWith.md)                         
      2. 数据类型
          * 基础
            * [15种原生对象类型系统综述](ECMA/types/typesOverview.md)
            * [原始值和复杂值](ECMA/types/primitiveValuesAndinvolutedValues.md)
            * [包装对象](ECMA/types/wrapperObjects.md)
          * 基础类型
            * [Undefined和Null](ECMA/types/UndefinedAndNull.md)
            * [Boolean布尔类型](ECMA/types/Boolean.md)
            * [Number数字类型](ECMA/types/Number.md)
            * [Math对象](ECMA/types/Math.md)
            * [String字符串类型](ECMA/types/String.md)
            * [String字符串类型的属性和方法](ECMA/types/StringOther.md)
          * 构造器类型
            * [正则表达式基础语法](ECMA/types/basicRegExp.md)
            * [RegExp正则类型](ECMA/types/RegExp.md)
            * [Array数组类型](ECMA/types/Array.md)
            * [22种数组方法](ECMA/types/ArrayOther.md)
            * [数组复制](ECMA/types/copyArray.md)
            * [字符串和数组的方法比较](ECMA/types/comparisonOfStringAndArray.md)
            * [错误处理机制](ECMA/types/Error.md)
          * 日期对象
            * [日期和时间基础知识](ECMA/types/basicDate.md)
            * [Date日期对象](ECMA/types/Date.md)
            * [简易日历实现](ECMA/types/Calendar.md)
            * [日期联动效果](ECMA/types/DateLinkage.md)    
          * 类型识别
            * [四种类型识别的方法](ECMA/types/typeRecognition.md)
            * [数组检测方式](ECMA/types/ArrayDetection.md)
          * 类型转换
            * [toString()](ECMA/types/toString.md)
            * [valueOf()](ECMA/types/valueOf.md)
            * [数据类型转换](ECMA/types/TypeConversions.md)  
          * 函数
            * [函数概述](ECMA/types/function.md)
            * [函数参数](ECMA/types/functionParameters.md)
            * [函数的属性和方法](ECMA/types/functionOther.md)
            * [ES6函数扩展](ECMA/types/functionES6.md)
            * [高阶函数](ECMA/types/higherOrderFunction.md)
            * [函数柯里化](ECMA/types/curring.md)
            * [函数节流和函数防抖](ECMA/types/debounceAndThrottle.md)
            * [惰性函数](ECMA/types/LazyFunction.md)
            * [函数式编程](ECMA/types/FunctionalProgramming.md)
          * 对象 
            * [初识对象](ECMA/types/Object.md)
            * [对象的属性操作](ECMA/types/objectAttr.md)
            * [对象的属性描述符](ECMA/types/objectPropertyDescriptor.md)
            * [对象拷贝](ECMA/types/objectCopy.md)
      3. 作用域
          * [内部原理](ECMA/scope/compilerTheory.md)
          * [词法作用域和动态作用域](ECMA/scope/lexicalAndDynamicScope.md)
          * [声明提升(hosting)](ECMA/scope/hosting.md)
          * [块作用域](ECMA/scope/blockScope.md)
          * [一张图理解执行环境和作用域](ECMA/scope/executionContextAndScope.md)
      4. 闭包
          * [到底什么才闭包](ECMA/closure/definition.md)
          * [从执行环境角度看闭包](ECMA/closure/definitionFromExecutionContext.md)
          * [IIFE](ECMA/closure/IIFE.md)
          * [常见的一个循环和闭包的错误详解](ECMA/closure/commonError.md)
          * [闭包的10种形式](ECMA/closure/allFormsOfClosure.md) 
      5. this
          * [this的4种绑定规则](ECMA/this/binding.md)
          * [this绑定优先级](ECMA/this/order.md)
          * [箭头函数](ECMA/this/ArrowFunction.md)
      6. 继承 
          * [一张图理解prototype、proto和constructor的三角关系](ECMA/inheritance/prototypeProtoAndConstructor.md)
          * [构造函数和原型对象](ECMA/inheritance/functionAndObject.md)
          * [创建对象的5种模式](ECMA/inheritance/createObject.md)
          * [实现继承的3种形式](ECMA/inheritance/inheritance.md)
          * [面向对象的6个概念](ECMA/inheritance/conception.md)
  * ES6
    * [介绍](ES6/ES6.md)
    * 类型扩展
        * [数字扩展](ES6/typeExtension/numberExtension.md)
        * [字符串扩展](ES6/typeExtension/stringExtension.md)
        * [模板字面量](ES6/typeExtension/templateLiteral.md)
        * [Unicode扩展](ES6/typeExtension/unicodeExtension.md)
        * [正则扩展](ES6/typeExtension/regExpExtension.md)
        * [函数扩展](ES6/typeExtension/functionExtension.md)
        * [对象扩展](ES6/typeExtension/objectExtension.md)
        * [Symbol类型](ES6/typeExtension/symbol.md)
        * [Set和Map集合](ES6/typeExtension/setAndMap.md)
        * [数组扩展](ES6/typeExtension/arrayExtension.md)
        * [定型数组](ES6/typeExtension/arrayBuffer.md)
    * 功能扩展
        * [块级作用域](ES6/abilityExtension/blockScope.md)
        * [解构赋值](ES6/abilityExtension/destructuring.md)
        * [类](ES6/abilityExtension/class.md)
        * [代理(Proxy)和反射(Reflection)](ES6/abilityExtension/proxyAndReflection.md)
        * [模块](ES6/abilityExtension/module.md)
        * [修饰器Decorator](ES6/abilityExtension/decorator.md)
    * 异步操作 
        * [迭代器(Iterator)和生成器(Generator)](ES6/async/IteratorAndGenerator.md)
        * [Promise和异步编程](ES6/async/promise.md)
        * [async](ES6/async/async.md)            
  * DOM
    1. 节点
        * 节点类型
          * [节点类型概述](DOM/node/nodeOverview.md)                          
          * [文本节点](DOM/node/textNode.md)
          * [注释节点和文档类型节点](DOM/node/commentAndDocumentTypeNode.md)
          * [文档片段节点](DOM/node/documentFragmentNode.md)
          * [元素节点](DOM/node/elementNode.md)
          * [特性节点](DOM/node/attrNode.md)               
          * [文档节点](DOM/node/documentNode.md)
        * 获取节点
          * [元素选择器](DOM/node/getElement.md)
          * [getElementsByClassName](DOM/node/className.md)
          * [selector选择器](DOM/node/selector.md)
          * [动态集合](DOM/node/DynamicCollection.md)
        * 节点操作
          * [节点关系](DOM/node/nodeRelation.md)
          * [节点操作](DOM/node/nodeOperation.md)
          * [节点内容](DOM/node/nodeContent.md)
          * [节点遍历](DOM/node/nodeThrough.md)
          * [节点范围](DOM/node/nodeRange.md)
          * [区分元素特性和对象属性](DOM/node/attrAndProperty.md)
    2. 脚本化CSS
        * [脚本化行间样式](DOM/CSSDOM/scriptingInlineStyles.md)
        * [查询计算样式](DOM/CSSDOM/queryingComputedStyles.md)
        * [脚本化CSS类](DOM/CSSDOM/scriptingCSSClasses.md)
        * [脚本化样式表](DOM/CSSDOM/scriptingStylesheets.md)
        * [动态样式](DOM/CSSDOM/dynamicStyles.md)
        * [脚本化伪元素](DOM/CSSDOM/scriptingPseudoElements.md)
    3. 元素尺寸
        * [偏移offset](DOM/size/offset.md)
        * [客户区Client](DOM/size/client.md)
        * [滚动Scroll](DOM/size/scroll.md)
        * [回到顶部](DOM/size/backToTop.md)
        * [元素视图方法](DOM/size/clientBounding.md)
    4. 事件
        * 事件机制
          * [事件流](DOM/event/eventFlow.md)
          * [事件处理程序](DOM/event/eventHandler.md)
          * [事件对象](DOM/event/eventObject.md)
          * [事件模拟](DOM/event/eventImitate.md)
        * 事件类型 
          * [鼠标事件](DOM/event/mouse.md)
          * [键盘事件](DOM/event/keyboard.md)
          * [变动事件](DOM/event/mutation.md)
          * [剪贴板事件](DOM/event/clipboard.md)
          * [文本事件](DOM/event/text.md)
          * [加载事件](DOM/event/load.md)
          * [焦点管理](DOM/event/focus.md)
  * BOM
    1. 定时器
        * [setTimeout()和setInterval()](BOM/setTimeoutAndSetInterval.md)
        * [requestAnimationFrame()](BOM/requestAnimationFrame.md)
        * [定时器应用(时钟、倒计时、秒表和闹钟)](BOM/timerApp.md)  
    2. window属性
        * [对话框](BOM/alert.md)
        * [窗口操作](BOM/window.md)
        * [location对象](BOM/location.md)
        * [history对象](BOM/history.md)
        * [screen对象](BOM/screen.md)
        * [navigator对象和用户代理检测](BOM/navigator.md)
        * [能力检测](BOM/abilityTest.md)
  * 模块化
    * [实现javascript下的模块组织](modular/ModuleOrganization.md)
    * [CommonJS规范及Node模块实现](modular/commonjs.md)
    * [使用Browserify来实现CommonJS的浏览器加载](modular/Browserify.md)
    * [AMD及requireJS](modular/requirejs.md)
    * [r.js打包](modular/r.md)
    * [CMD及seaJS](modular/seajs.md)
    * [ES6中的Module](modular/es6Modula.md)