<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h2>4.1、嵌套规则</h2>
    <section>
      <div id="main1">
        <p>嵌套规则 (Nested Rules)
          <span class="redbox">嵌套功能避免了重复输入父选择器，而且令复杂的 CSS 结构更易于管理：</span>
        </p>
      </div>
    </section>
    <h2>4.2、 父选择器 & </h2>
    <section>
      <div id="main2">
        父选择器 & (Referencing Parent Selectors: &)
        <a href="#">在嵌套 CSS 规则时，有时也需要直接使用嵌套外层的父选择器，例如，当给某个元素设定 hover 样式时，或者当 body 元素有某个 classname 时，可以用 & 代表嵌套规则外层的父选择器。</a>
      </div>
    </section>
    <h2>4.3、属性嵌套</h2>
    <section>
      <div class="funky">
        有些 CSS 属性遵循相同的命名空间 (namespace)，比如 font-family, font-size, font-weight 都以 font 作为属性的命名空间。为了便于管理这样的属性，同时也为了避免了重复输入，Sass 允许将属性嵌套在命名空间中，例如：
      </div>
    </section>
    <h2>4.4、占位符选择器%</h2>
    <section>
      Sass 额外提供了一种特殊类型的选择器：占位符选择器 (placeholder selector)。与常用的 id 与 class 选择器写法相似，只是 # 或 . 替换成了 %。必须通过 @extend 指令调用，
    </section>
    <h2>5、注释 /* */ 与 //</h2>
    <section>Sass 支持标准的 CSS 多行注释 /* */，以及单行注释 //，前者会 被完整输出到编译后的 CSS 文件中，而后者则不会</section>
    <h2>6. SassScript</h2>
    <h2>6.1. Interactive Shell</h2>
    <h2>6.2. 变量 $</h2>
    <section>
      <div id="main3">
        SassScript 最普遍的用法就是变量，变量以美元符号开头，赋值方法与 CSS 属性的写法一样：
      </div>
      <div id="main4">
        变量支持块级作用域，嵌套规则内定义的变量只能在嵌套规则内使用（局部变量），不在嵌套规则内定义的变量则可在任何地方使用（全局变量）。将局部变量转换为全局变量可以添加 !global 声明：
      </div>
      <div id="sidebar"></div>
    </section>
    <h2>6.3. 数据类型 (Data Types)</h2>
    <h3>6.3.1. 字符串</h3>
    <section>
      <div class="header">SassScript 支持 CSS 的两种字符串类型：有引号字符串 (quoted strings)，如 "Lucida Grande" 'http://sass-lang.com'；与无引号字符串 (unquoted strings)，如 sans-serif bold，在编译 CSS 文件时不会改变其类型。只有一种情况例外，使用 #{} (interpolation) 时，有引号字符串将被编译为无引号字符串，这样便于在 mixin 中引用选择器名：</div>
    </section>
    <h3>6.3.2. 数组</h3>
    <h3>6.3.3. Maps</h3>
    <h3>6.3.4. 颜色</h3>
    <h2>6.4. 运算</h2>
    <h3>6.4.1. 数字运算</h3>
    <section>
      <div id="main5">
        <p>SassScript 支持数字的加减乘除、取整等运算 (+, -, *, /, %)，如果必要会在不同单位间转换值。</p>
      </div>
    </section>
    <h4>6.4.1.1. 除法运算</h4>
    <div id="main6">
      <p>/ 在 CSS 中通常起到分隔数字的用途，SassScript 作为 CSS 语言的拓展当然也支持这个功能，同时也赋予了 / 除法运算的功能。也就是说，如果 / 在 SassScript 中把两个数字分隔，编译后的 CSS 文件中也是同样的作用</p>
    </div>
    <h3>6.4.3. 字符串运算 </h3>
    <div id="main7">
      <p>注意，如果有引号字符串（位于 + 左侧）连接无引号字符串，运算结果是有引号的，相反，无引号字符串（位于 + 左侧）连接有引号字符串，运算结果则没有引号。</p>
    </div>
    <h3>6.5. 圆括号</h3>
    <section>
      <div id="main8">
        <p>圆括号可以用来影响运算的顺序：</p>
      </div>
    </section>
    <h3>6.6. 函数</h3>
    <h3>6.7. 插值语句 #{}</h3>
    <section>
      <div id="main9">
        <p class="foo">通过 #{} 插值语句可以在选择器或属性名中使用变量：</p>
      </div>
    </section>
    <h2>7. @-Rules 与指令</h2>
    <h3>7.1. @import</h3>
    <h3>7.2. @media</h3>
    <section>
      <div id="main10">
        <p>Sass 中 @media 指令与 CSS 中用法一样，只是增加了一点额外的功能：允许其在 CSS 规则中嵌套。如果 @media 嵌套在 CSS 规则内，编译时，@media 将被编译到文件的最外层，包含嵌套的父选择器。这个功能让 @media 用起来更方便，不需要重复使用选择器，也不会打乱 CSS 的书写流程。</p>
      </div>
    </section>
    <h3>7.3. @extend</h3>
    <div id="main11">
      <div class="seriousError">
        Oh no! You've been hacked!
      </div>
    </div>
    <h3>7.4. @at-root</h3>
    <h2>8. 控制指令</h2>
    <p>SassScript 提供了一些基础的控制指令，比如在满足一定条件时引用样式，或者设定范围重复输出格式。控制指令是一种高级功能，日常编写过程中并不常用到，主要与混合指令 (mixin) 配合使用，尤其是用在 Compass 等样式库中。</p>
    <h3>8.1. if()</h3>
    <h3>8.2. @if</h3>
    <section>
      <div id="main12">
        <p>当 @if 的表达式返回值不是 false 或者 null 时，条件成立，输出 {} 内的代码：</p>
      </div>
    </section>
    <section>
      <div id="main13">
        <p>@if 声明后面可以跟多个 @else if 声明，或者一个 @else 声明。如果 @if 声明失败，Sass 将逐条执行 @else if 声明，如果全部失败，最后执行 @else 声明，例如：</p>
      </div>
    </section>
    <h3>8.3. @for</h3>
    <section>
      <p>@for 指令可以在限制的范围内重复输出格式，每次按要求（变量的值）对输出结果做出变动。这个指令包含两种格式：@for $var from 'start' through 'end'，或者 @for $var from 'start' to 'end'，区别在于 through 与 to 的含义：当使用 through 时，条件范围包含 'start' 与 'end' 的值，而使用 to 时条件范围只包含 'start' 的值不包含 'end' 的值。另外，$var 可以是任何变量，比如 $i；'start' 和 'end' 必须是整数值。'</p>
      <div id="main14">
        <ul>
          <li class="item-1">指令可以在限制的范围内重复输出格式，每次按要求（变量的值）对输出结果做出变动。</li>
          <li class="item-2">指令可以在限制的范围内重复输出格式，每次按要求（变量的值）对输出结果做出变动。</li>
          <li class="item-3">指令可以在限制的范围内重复输出格式，每次按要求（变量的值）对输出结果做出变动。</li>
        </ul>
      </div>
    </section>
    <h3>8.4. @each</h3>
    <section>
      <div id="main15">
        <p>@each 指令的格式是 $var in 'list', $var 可以是任何变量名，比如 $length 或者 $name，而 'list' 是一连串的值，也就是值列表。</p>
        <div class="puma-icon"></div>
        <div class="sea-slug-icon"></div>
        <div class="egret-icon"></div>
        <div class="salamander-icon"></div>
      </div>
    </section>
    <h3>8.5. @while</h3>
    <section>
      <div id="main16">
        <ul>
          <li class="item-1"></li>
          <li class="item-2"></li>
          <li class="item-3"></li>
          <li class="item-4"></li>
          <li class="item-5"></li>
          <li class="item-6"></li>
        </ul>
      </div>
    </section>
    <h2>9. 混合指令</h2>
    <section>
      <p>混合指令（Mixin）用于定义可重复使用的样式，避免了使用无语意的 class，比如 .float-left。混合指令可以包含所有的 CSS 规则，绝大部分 Sass 规则，甚至通过参数功能引入变量，输出多样化的样式。</p>
    </section>
    <h3>9.1. 定义混合指令</h3>
    <section>
      <p>混合指令的用法是在 @mixin 后添加名称与样式，比如名为 large-text 的混合通过下面的代码定义：</p>
    </section>
    <h3>9.2. 引用混合样式 @include</h3>
    <section>
      <div class="page-title">使用 @include 指令引用混合样式，格式是在其后添加混合名称，</div>
    </section>
    <h3>9.3. 参数 (Arguments)</h3>
    <section>
      <div id="main17">
        <p>参数用于给混合指令中的样式设定变量，并且赋值使用。在定义混合指令的时候，按照变量的格式，通过逗号分隔，将参数写进圆括号里。引用指令时，按照参数的顺序，再将所赋的值对应写进括号：</p>
        <h4>混合指令也可以使用给变量赋值的方法给参数设定默认值，然后，当这个指令被引用的时候，如果没有给参数赋值，则自动使用默认值：</h4>
      </div>
    </section>
    <h4>9.3.1. 关键词参数</h4>
    <h4>9.3.2. 参数变量</h4>
    <section>
      <p class="shadows">有时，不能确定混合指令需要使用多少个参数，比如一个关于 box-shadow 的混合指令不能确定有多少个 'shadow' 会被用到。这时，可以使用参数变量 … 声明（写在参数的最后方）告诉 Sass 将这些参数视为值列表处理：</p>
    </section>
    <h2>10. 函数指令</h2>
    <section>
      <div id="main18">
        <p>Sass 支持自定义函数，并能在任何属性值或 Sass script 中使用：</p>
      </div>
    </section>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import '@/assets/main.scss';

export default {
  name: 'App',
  components: {
    // HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
