# radium

`npm install radium --save`
# 使用方法

###  1.引入

    ```
    
    var Radium = require('radium');

    // or
    import Radium from 'radium'


    import Radium from 'radium'
    
    ```

###  2.导出

    ```
    // For ES6 and ES7
    @Radium
    class Button extends React.Component {
      // ...
    }

    // or
    class Button extends React.Component {
      // ...
    }
    module.exports = Radium(Button);

    // or
    class Button extends React.Component {
      // ...
    }
    export default radium(Button)

    ```

> Radium supports styling for three browser states that are targeted with pseudo-selectors in normal CSS: :hover, :focus, and :active.

radium 可以支持三个伪类 `:hover :focus :active`

```

var styles = {
  base: {
    background: 'blue',
    border: 0,
    borderRadius: 4,
    color: 'white',
    padding: '1.5em',

    ':hover': {
      backgroundColor: 'red'
    },

    ':focus': {
      backgroundColor: 'green'
    },

    ':active': {
      backgroundColor: 'yellow'
    },
  },

  block: {
    display: 'block',

    ':hover': {
      boxShadow: '0 3px 0 rgba(0,0,0,0.2)'
    }
  },
  
};

```

> Add media queries to your style objects the same way as you would add browser state modifiers like :hover. The key must start with @media, and the syntax is identical to CSS:

radium支持媒体查询
```

var style = {
  width: '25%',

  '@media (min-width: 320px)': {
    width: '100%'
  }
};

```
> Media query styles can also contain nested browser states:

媒体查询可以嵌套 `:hover :focus :active`
```
var style = {
  width: '25%',

  '@media (min-width: 320px)': {
    width: '100%',

    ':hover': {
      background: 'white'
    }
  }
};

```
> Then, include that style object in the array passed to the style attribute if the conditions match:

可以在render方法中 返回的标签的style中写入一个数组,数组之中的元素必须是对象
```
render(){
    return (
      <button
        style={[
          styles.base,
          styles.block
        ]}>
        {this.props.children}
      </button>
    );
}

```


