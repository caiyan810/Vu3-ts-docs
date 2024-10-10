## 基本概念
VueUse 的基础概念主要围绕 Vue 3 的组合式 API (Composition API) 构建，它为 Vue 开发者提供了许多实用函数和工具，方便操作状态、事件、浏览器 API 等。以下是一些 VueUse 的基础概念和关键点：

1. 组合式函数（Composables）
VueUse 的核心是 "组合式函数"（也称为 Composables）。这是 Vue 3 中的一个重要概念，允许开发者将可复用的逻辑提取为独立的函数。这些函数通常与 Vue 的响应式系统一起使用，可以方便地共享逻辑并保持代码清晰。

例如，useMouse 组合式函数可以监听鼠标位置，并自动更新其响应式数据：
import { useMouse } from '@vueuse/core'

export default {
  setup() {
    const { x, y } = useMouse()  // x 和 y 是响应式的数据
    return { x, y }
  },
}

2. 响应式（Reactivity）
VueUse 中所有的组合式函数都基于 Vue 的响应式系统。返回的数据都是响应式的，这意味着当状态发生变化时，依赖该状态的组件会自动更新，无需手动管理。

例如，useWindowSize 可以获取窗口的宽度和高度，并自动响应窗口大小的变化：
import { useWindowSize } from '@vueuse/core'

export default {
  setup() {
    const { width, height } = useWindowSize()  // 宽度和高度是响应式的
    return { width, height }
  },
}

3. 按需加载（Tree Shaking）
VueUse 模块化设计，可以按需引入，避免加载不必要的代码，从而优化项目性能。只需要安装 VueUse 后，通过 ES6 模块语法引入特定的组合式函数。
import { useStorage } from '@vueuse/core'
这使得使用 VueUse 时不必担心性能问题，因为只会引入所需的函数，而不引入其他部分。

4. 与浏览器 API 的结合
VueUse 提供了对许多浏览器原生 API 的封装，使其与 Vue 的响应式系统集成。例如，useLocalStorage 和 useSessionStorage 提供了对本地存储和会话存储的响应式封装。
import { useLocalStorage } from '@vueuse/core'
export default {
  setup() {
    const name = useLocalStorage('name', 'default')  // 存储键为 'name'
    return { name }
  },
}1

5. 插件和扩展
VueUse 除了核心库，还有很多插件模块，如：

@vueuse/head：用于管理页面 head 标签的工具，可以方便地动态修改页面的标题、meta 信息等。
@vueuse/router：与 Vue Router 集成的工具。
@vueuse/integrations：与第三方库（如 Firebase、Axios 等）结合使用的集成工具。
6. TypeScript 支持
VueUse 完全支持 TypeScript，所有的组合式函数都有完善的类型声明，方便类型安全的开发体验。你可以通过类型推导明确知道函数返回的数据类型，减少开发中出现的错误。

7. VueUse 与 Vue 生态的深度集成
VueUse 针对 Vue 3 做了高度的优化，同时也能配合其他 Vue 生态工具（如 Pinia、Vue Router 等）使用，增强 Vue 项目的功能扩展性和易用性。

8. 实用的工具函数
除了大部分操作浏览器 API 的组合式函数，VueUse 还提供了许多实用的工具函数，比如：

useToggle：开关状态管理。
useDebounce 和 useThrottle：为函数添加防抖和节流效果。

这些基础概念使 VueUse 成为 Vue 3 开发中非常实用的工具，尤其在使用组合式 API 时能够极大提升开发效率。