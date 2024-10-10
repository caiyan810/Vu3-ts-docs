## 安装
1. 使用 npm 或 yarn 安装
npm 安装
npm install @vueuse/core

2. 在项目中引入 VueUse
安装完成后，就可以在你的 Vue 3 项目中按需使用 VueUse 的各种组合式函数。例如：
import { useMouse } from '@vueuse/core'

export default {
  setup() {
    const { x, y } = useMouse()
    return { x, y }
  },
}

3. 按需引入插件
VueUse 提供了许多模块，你可以根据项目需要选择性地引入，而不必全部引入，以减小项目体积。