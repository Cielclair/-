# Vue Test Utils

> [Doc](https://vue-test-utils.vuejs.org/zh/)

### 挂载组件

> Vue Test Utils 通过将它们
>
> 1. 隔离挂载，
> 2. 然后模拟必要的输入 (prop、注入和用户事件) 
> 3. 和对输出 (渲染结果、触发的自定义事件) 的**断言**
>
> 来测试 Vue 组件。

?>被挂载的组件会返回到一个[包裹器](https://vue-test-utils.vuejs.org/zh/api/wrapper/)内，而包裹器会暴露很多封装、遍历和查询其内部的 Vue 组件实例的便捷的方法。

你可以通过 `mount` 方法来创建包裹器。



### 测试组件渲染出来的 HTML

### 模拟用户交互

# Wrapper

Vue Test Utils 是一个基于包裹器的 API。

一个 `Wrapper` 是一个包括了一个挂载组件或 vnode，以及测试该组件或 vnode 的方法。



## trigger

Triggers an event asynchronously on the `Wrapper` DOM node.

trigger` takes an optional `options` object. The properties in the `options` object are added to the Event. `trigger` returns a Promise, which when resolved, guarantees the component is updated. `trigger` only works with native DOM events. To emit a custom event, use `wrapper.vm.$emit('myCustomEvent')

- **Arguments:**
  - `{string} eventType` **required**
  - `{Object} options` **optional**
- **Example:**

```js
import { mount } from '@vue/test-utils'
import sinon from 'sinon'
import Foo from './Foo'

test('trigger demo', async () => {
  const clickHandler = sinon.stub()
  const wrapper = mount(Foo, {
    propsData: { clickHandler }
  })

  await wrapper.trigger('click')

  await wrapper.trigger('click', {
    button: 0
  })

  await wrapper.trigger('click', {
    ctrlKey: true // For testing @click.ctrl handlers
  })

  expect(clickHandler.called).toBe(true)
})
```

- **Setting the event target:**

Under the hood, `trigger` creates an `Event` object and dispatches the event on the Wrapper element.

It's not possible to edit the `target` value of an `Event` object, so you can't set `target` in the options object.

To add an attribute to the `target`, you need to set the value of the Wrapper element before calling `trigger`. You can do this with the `element` property.

```js
const input = wrapper.find('input')
input.element.value = 100
input.trigger('click')
```