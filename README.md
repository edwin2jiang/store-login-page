# Vue 3 + TypeScript + Vite

## 登录界面

![image-20220830091744310](http://imgbed-xia-2.oss-cn-hangzhou.aliyuncs.com/img/2022/08/30/20220830-091746.png)



## 必要前提

### 安转unocss

### Vite

```
npm i -D unocss
// vite.config.ts
import Unocss from 'unocss/vite'

export default {
  plugins: [
    Unocss({ /* options */ }),
  ],
}
```

Add `uno.css` to your main entry:

```
// main.ts
import 'uno.css'
```

