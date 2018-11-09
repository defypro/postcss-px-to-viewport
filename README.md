##### 在[postcss-px-to-viewport](https://github.com/evrone/postcss-px-to-viewport)基础上增加exclude配置项，可以忽略指定文件夹
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
- `viewportWidth` (Number) 视窗的宽度，对应的是我们设计稿的宽度，一般是 750
- `viewportHeight` (Number) 视窗的高度，根据 750 设备的宽度来指定，一般指定 1334，也可以不配置。
- `unitPrecision` (Number) 指定`px`转换为视窗单位值的小数位数（很多时候无法整除）。
- `viewportUnit` (String) 指定需要转换成的视窗单位，建议使用 vw
- `selectorBlackList` (Array) 指定不转换为视窗单位的类，可以自定义，可以无限添加,建议定义一至两个通用的类名。
  - 如果 value 是 string，则检查 selector 是否包含字符串。
    - `['body']` 将会匹配 `.body-class`
  - 如果 value 是 regexp，它会检查选择器是否与正则表达式匹配。
    - `[/^body$/]` 将会匹配 `body` 并不是 `.body`
- `minPixelValue` (Number) 小于或等于`1px`不转换为视窗单位，你也可以设置为你想要的值。
- `mediaQuery` (Boolean) 允许在媒体查询中转换`px`
- `exclude` (RegExp) 排除路径不参与转换 eg:`/(\/|\\)(node_modules)(\/|\\)/`