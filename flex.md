# flex 布局学习

=========

* 该学习笔记参考整理自  <a href="http://www.gbtags.com/gb/gbtutorials/48.htm">极客标签:flexbox布局的缺省布局方向</a>，感谢分享。

* 什么是flex

    Flexible Box布局，简称flexbox布局，它是一种新的布局方式，并且提供很多新特性。

    * 支持任意方向的布局（左，右，下及其上）
    * 支持视觉上的反向和重新布局
    * 支持自适应各种不同空间
    * 可以针对容器对齐
    * 拥有统一的高度

* 怎么定义flex*
    ```
        display: flex;
        display: -webkit-flex; 
    ```

* flex布局使用示例
 
    ```
        .flexboxlayout {
            display: flex;
            display:-webkit-flex;
            flex-direction:row;
            -webkit-flew-direction: row;
        }
        
        .flexboxlayout > .item {
            width: 300px;
            height: 300px;
            background: #dddddd;
            margin: 5px;
        }
        div class="flexboxlayout">
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
        </div>
    ```

    备注：
    
    * 如果修改子元素item的宽度，他们并不会溢出父元素，只会适应父元素。除非父元素的宽度变化，子元素才会修改自身的宽度来适应。
    * 可以通过设置flex-direction为column，将flexbox的整体布局设置为纵向

* flexbox **纵向布局**中控制子元素的对齐方式

    * align-items 控制纵向布局中子元素的上下对齐方式，取值 flex-start，flex-end
    * justify-content 控制纵向布局中子元素的左右对齐方式，取值 flex-start，flex-end
    
    ```
        .flexboxlayout {
            display: flex;
            display:-webkit-flex;
            flex-direction: column;
            align-items: flex-end;
            justify-content: flex-end;
            height: 600px;
            background: #ddd;
        }
        
        .flexboxlayout > .item {
            width: 300px;
            height: 50px;
            background: orange;
            margin: 5px;
        }
        
        <div class="flexboxlayout">
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
        </div>
    
    ```
* flexbox **横向布局**中控制子元素的对齐方式

    * align-items
    * justify-content 
    
    ```
        .flexboxlayout {
            display: flex;
            display:-webkit-flex;
            flex-direction: row;
            align-items: flex-end;
            justify-content: flex-end;
            height: 400px;
            background: #ddd;
        }
        
        .flexboxlayout > .item {
            width: 50px;
            height: 50px;
            background: orange;
            margin: 5px;
        }
        
        <div class="flexboxlayout">
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
        </div>
    
    ```
* 实现子元素绝对居中效果

    *  align-items: center;
    *  justify-content: center;
    
    ```
        .flexboxlayout {
            display: flex;
            display:-webkit-flex;
            flex-direction: row;
            align-items: center;
            justify-content: center;
            height: 400px;
            background: #ddd;
        }
        
        .flexboxlayout > .item {
            width: 50px;
            height: 50px;
            background: orange;
            margin: 5px;
        }
        
         <div class="flexboxlayout">
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
        </div>
    ```
    
* 设置子元素的宽度比例
    
    ```
        .flexboxlayout {
            display: flex;

            width: 500px;
            height: 500px;
            background: #ddd;
            padding: 10px;
        }

        .sidebar {
            flex: 1 0 0;
            background: orange;
        }

        .content {
            flex:2 0 0;
            background: #dd4814;
        }
        
        <div class="flexboxlayout">
            <div class="content"></div>
            <div class="sidebar"></div>
        </div>
    ```
    
* 控制flex子元素的横纵向折行后果

    * flex-wrap：wrap
    * flex-flow: row wrap/column wrap  可以理解为flex-direction和flew-wrap的效果集合
    * align-content: stretch/flex-start/flex-end/space-around/space-between
    
    ```
        .flexboxlayout {
            display: flex;

            align-items: center;
            justify-content: center;

            /*以下定义折行*/
            flex-wrap: wrap;  
            
            flex-flow: column wrap;/*缺省默认是row wrap*/
            -webkit-flex-flow: column wrap;
    
            /* 下面我们可以调整子元素的对齐方式，使用align-content属性*/
            /* 合法的值可以是：flex-start, flex-end, space-between, space-around, stretch*/

            align-content: stretch;
            -web-flex-wrap: stretch;
            
            background: #ddd;
            height: 300px;
            width: 500px;
        }

        .flexboxlayout > .item {
            width: 50px;
            height: 50px;
            background: orange;
            margin: 5px;
        }
        
        <div class="flexboxlayout">
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
            <div class="item"></div>
        </div>
    
    ```
    