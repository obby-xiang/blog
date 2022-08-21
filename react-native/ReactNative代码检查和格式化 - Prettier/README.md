# ReactNative代码检查和格式化 - Prettier

## Prettier简介

Prettier是一个代码格式化工具，它能删除所有原始样式并确保所有输出的代码符合一致的样式。

```jsx
function HelloWorld({greeting = "hello", greeted = '"World"', silent = false, onMouseOver,}) {

  if(!greeting){return null};

     // TODO: Don't use random in render
  let num = Math.floor (Math.random() * 1E+7).toString().replace(/\.\d+/ig, "")

  return <div className='HelloWorld' title={`You are visitor number ${ num }`} onMouseOver={onMouseOver}>

    <strong>{ greeting.slice( 0, 1 ).toUpperCase() + greeting.slice(1).toLowerCase() }</strong>
    {greeting.endsWith(",") ? " " : <span style={{color: '\grey'}}>", "</span> }
    <em>
	{ greeted }
	</em>
    { (silent)
      ? "."
      : "!"}

    </div>;

}
```

```jsx
function HelloWorld({
  greeting = "hello",
  greeted = '"World"',
  silent = false,
  onMouseOver,
}) {
  if (!greeting) {
    return null;
  }

  // TODO: Don't use random in render
  let num = Math.floor(Math.random() * 1e7)
    .toString()
    .replace(/\.\d+/gi, "");

  return (
    <div
      className="HelloWorld"
      title={`You are visitor number ${num}`}
      onMouseOver={onMouseOver}
    >
      <strong>
        {greeting.slice(0, 1).toUpperCase() + greeting.slice(1).toLowerCase()}
      </strong>
      {greeting.endsWith(",") ? (
        " "
      ) : (
        <span style={{ color: "grey" }}>", "</span>
      )}
      <em>{greeted}</em>
      {silent ? "." : "!"}
    </div>
  );
}
```



## React Native项目安装Prettier

React Native项目中使用的Prettier版本可在`node_modules/react-native/package.json`文件中查看，以React Native 0.69.3为例，使用的Prettier版本为`^2.4.1`（即`>=2.4.1 <2.5.0`）。

在项目中安装对应版本的Prettier。

```shell
yarn add --dev prettier@^2.4.1
# or
npm install --save-dev prettier@^2.4.1
```

> 不建议全局安装Prettier或使用全局安装的Prettier，因为各项目中使用的Prettier版本可能不同。



## 参考

- [Docs - Prettier](https://prettier.io/docs/en/index.html)

