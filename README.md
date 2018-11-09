##### 在(postcss-px-to-viewport)[https://github.com/evrone/postcss-px-to-viewport]基础上增加exclude配置项，可以忽略指定文件夹
```
"postcss-px-to-viewport": {
      viewportWidth: 750,
      viewportHeight: 1334,
      unitPrecision: 3,
      viewportUnit: 'vw',
      selectorBlackList: ['.ignore', '.hairlines'],
      minPixelValue: 1,
      mediaQuery: false,
      exclude: /(\/|\\)(node_modules)(\/|\\)/
    },
```