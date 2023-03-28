---
title: 'EventSource: message event'
slug: Web/API/EventSource/message_event
page-type: web-api-event
tags:
  - API
  - Event
  - EventSource
  - Reference
  - message
browser-compat: api.EventSource.message_event
---
{{APIRef}}

当通过事件源接收数据时，将触发{{domxref（“EventSource”）}}API的消息事件。``

此事件不可取消，也不会冒泡。

## 句法

在{{domxref（“EventTarget.addEventListener”、“addEventListener（）”）}}等方法中使用事件名称，或设置事件处理程序属性。

```js
addEventListener（’message’，（event）=>{}）；

onmessage=（event）=>{}；
```

## 事件类型

{{domxref（“MessageEvent”）}}。从{{domxref（“Event”）}}继承。

{{InheritanceDiagram（“MessageEvent”）}}

## 事件属性

_此接口还从其父接口{{domxref（“Event”）}}继承属性。_

- {{domxref（“MessageEvent.data”）}}{{readonlyInline}}
   - ：消息发射器发送的数据。
- {{domxref（“MessageEvent.origin”）}}{{readonlyInline}}
   - ：表示消息发射器来源的字符串。
- {{domxref（“MessageEvent.lastEventId”）}}{{readonlyInline}}
   - ：表示事件的唯一ID的字符串。
- {{domxref（“MessageEvent.source”）}}{{readonlyInline}}
   - ：表示消息发射器得MessageEventSource（可以是{{domxref（“WindowProxy”）}}、{{domxref（“MessagePort”）}}或{{domxref（“ServiceWorker”）}}对象）。``
- {{domxref（“MessageEvent.ports”）}}{{readonlyInline}}
   - ：{{domxref（“MessagePort”）}}对象数组，表示与发送消息的通道相关联的端口（在适当的情况下，例如在通道消息传递中或向共享工作线程发送消息时）。

## 例子

在这个基本示例中，创建了一个EventSource来接收来自服务器的事件；名为sse.php的页面负责生成事件。````

```js
const evt source=new event source（’sse.php’）；
const event list=document.query selector（’ul’）；

evtSource.addEventListener('message'，(e)=>{
const newElement=document.createElement（“li”）；

  新元素。text content=`message：${e.data}`；
事件列表。appendChild（newElement）；
});
```

### onmessage等价物

```js
evtSource.onmessage=（e）=>{
const newElement=document.createElement（“li”）；
  新元素。text content=`message：${e.data}`；
事件列表。appendChild（newElement）；
};
```

## 规格

{{规格}}

## 浏览器兼容性

{{Compat}}

## 另请参阅

- [使用服务器发送的事件](/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events)
- [`打开`](/en-US/docs/Web/API/EventSource/open_event)
- [`错误`](/en-US/docs/Web/API/EventSource/error_event)
