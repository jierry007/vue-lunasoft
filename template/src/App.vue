<template>
  <div id="app">
    {{#router}}
    <router-view/>
    {{else}}
    <hello-world/>
    {{/router}}
  </div>
</template>

<script>
{{#unless router}}
import HelloWorld from './components/HelloWorld'{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
{{/unless}}
export default {
  name: 'app'{{#router}}{{#if_eq lintConfig "airbnb"}},{{/if_eq}}{{else}},
  components: {
    HelloWorld{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
  }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}{{/router}}
}{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
</script>

<style>
  #app {
    font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    font-size: 14px;
    width: 100%;
  }
  html, body {
    min-width: 1024px;
    width: 100%;
  }
  
  /* 重置文本格式元素 */
  a { text-decoration: none; }
  
  /* 清除内外边距 */
  body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, /* structural elements 结构元素 */
  dl, dt, dd, ul, ol, li, /* list elements 列表元素 */
  pre, /* text formatting elements 文本格式元素 */
  fieldset, lengend, button, input, textarea, /* form elements 表单元素 */
  th, td { /* table elements 表格元素 */
    margin: 0;
    padding: 0;
  }
  
  /* 重置表单元素 */
  legend { color: #000; } /* for ie6 */
  fieldset, img { border: none; } /* img 搭车：让链接里的 img 无边框 */
  /* 注：optgroup 无法扶正 */
  button, input, select, textarea {
    font-size: 100%; /* 使得表单元素在 ie 下能继承字体大小 */
  }
  
  /* 重置表格元素 */
  table {
    border-collapse: collapse;
    border-spacing: 0;
  }
  
  /* 重置列表元素 */
  ul, ol { list-style: none; }
</style>
