## 介绍
VueUse 是一个基于 Vue 3 的实用函数库，专注于组合式 API（Composition API）。它提供了大量开箱即用的组合函数（composables），简化了常见的开发任务，如状态管理、事件监听、浏览器 API 的使用、媒体控制等。VueUse 可以帮助开发者快速集成各种功能，而无需重复编写大量底层逻辑。

VueUse 的主要特点：
丰富的组合式函数：内置了 200 多个功能强大的 composables，涵盖各种开发场景。
响应式 API：所有 composables 都基于 Vue 的响应式系统，支持自动追踪依赖并更新 UI。
良好的 TypeScript 支持：VueUse 具备完善的 TypeScript 类型推导，方便类型安全开发。
轻量化：虽然功能丰富，但它的设计非常轻量，不会对应用性能造成负担。
灵活的模块化：可以按需引入，减少不必要的代码加载。
常用功能示例：
状态管理：useStorage 可以轻松将数据保存到本地存储（LocalStorage 或 SessionStorage），并且数据变化时自动同步到存储中。
DOM 操作：useMouse 用来监听鼠标位置的变化，useWindowSize 则能实时获取窗口的大小。
时间与日期：useNow 能持续获取当前时间的响应式数据，适用于时钟、定时器等场景。
媒体控制：useMediaQuery 可以监控媒体查询（如检测设备是手机还是桌面），useFullscreen 用来管理全屏模式。