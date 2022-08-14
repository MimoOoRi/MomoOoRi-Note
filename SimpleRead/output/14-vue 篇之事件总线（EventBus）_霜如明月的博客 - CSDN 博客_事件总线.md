> [vue 篇之事件总线（EventBus）_霜如明月的博客 - CSDN 博客_事件总线](https://blog.csdn.net/q3254421/article/details/82927860?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3-82927860-blog-118885935.pc_relevant_aa&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3-82927860-blog-118885935.pc_relevant_aa&utm_relevant_index=6)
    Tags:
    Date:  [[2022_05_06  ]]
    Describe:许多现代JavaScript框架和库的核心概念是能够将数据和UI封装在模块化、可重用的组件中。这对于开发人员可以在开发整个应用程序时避免使用编写大量重复的代码。虽然这样做非常有用，但也涉及到组件之间的数据通讯。在Vue中同样有这样的概念存在。通过前面一段时间的学习，Vue组件数据通讯常常会有父子组件，兄弟组件之间的数据通讯。也就是说在Vue中组件通讯有一定的原则。父子组件通讯原则为了提高组件的...

- >引入 Vue 并导出它的一个实例（在这种情况下，我称它为 `EventBus` ）。实质上它是一个不具备 DOM 的组件，它具有的仅仅只是它实例方法而已，因此它非常的轻便。
	-
	-
- >使用 `EventBus.$off(‘decreased’)` 来移除应用内所有对此事件的监听。或者直接调用`EventBus.$off()` 来移除所有事件频道， **注意不需要添加任何参数** 。
	-
	-
- >所有组件都能够将事件发布到总线，然后总线由另一个组件订阅，然后订阅它的组件将得到更新
	-
	-
-
-