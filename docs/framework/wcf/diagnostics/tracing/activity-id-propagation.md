---
title: 活动 ID 传播
ms.date: 03/30/2017
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
ms.openlocfilehash: e51970f693d9ca2d2f81bf4efc97969896de4828
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="activity-id-propagation"></a>活动 ID 传播
当 ServiceModel 活动跟踪启用（ServiceModel 传播）或禁用（用户对用户活动跟踪）时，都会发生传播。  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a>ServiceModel 活动跟踪启用  
 如果启用 ServiceModel ActivityTracing，传播将在 ProcessAction 活动之间发生。  
  
### <a name="server"></a>服务器  
 当`propagateActivity`属性设置为`true`上的客户端和服务器的 ID`ProcessAction`服务器中的活动是在与传播的 ID 相同`ActivityId`消息标头。  
  
 未`ActivityId`标头消息中存在时 (即， `propagateActivity` = `false`客户端上)，或当`propagateActivity` = `false`在服务器上，服务器会生成一个新的活动 id。  
  
### <a name="client"></a>客户端  
 如果客户端是同步单线程，则客户端忽略客户端或服务器上 `propagateActivity` 的任何设置。 响应则改为在请求活动中处理。 如果客户端是异步或同步多线程， `propagateActivity` = `true`在客户端，并且由服务器发送的消息中没有活动 ID 标头，客户端从消息中，检索活动 ID，然后转移到处理包含传播的活动 ID 的操作活动 否则，客户端从“进程管理”活动转移到新的“进程操作”活动。 完成到新“进程操作”活动的这一额外转移是为了实现一致性。 在此活动内，如果为响应消息处理分配了线程，则客户端从本地线程上下文检索 BeginCall 活动的活动 ID。 然后，客户端转移到初始“进程操作”活动。  
  
 如果客户端为双工，则客户端在接收消息时用作服务器。  
  
### <a name="propagation-in-fault-messages"></a>错误消息中的传播  
 有效消息和错误消息的处理没有任何区别。 如果`propagateActivity` = `true`，添加到 SOAP 错误消息头的活动 ID 等同于环境的活动。  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a>ServiceModel 活动跟踪禁用  
 如果 ServiceModel ActivityTracing 禁用，传播将在用户代码活动之间直接发生，而不经过 ServiceModel 活动。 用户定义的活动 ID 也通过消息活动 ID 标头传播。  
  
 如果`propagateActivity` = `true`和`ActivityTracing` = `off` ServiceModel 跟踪侦听器 （无论 ServiceModel 上是否启用跟踪），发生以下情况客户端或服务器上：  
  
-   在操作请求或发送响应时，TLS 中的活动 ID 从用户代码传播出去，直至构成消息。 活动 ID 标头也在消息发送之前插入消息中。  
  
-   接收到请求或响应时，只要创建了接收的消息对象，即从消息头中检索活动 ID。 消息从作用域中一消失，TLS 中的活动 ID 就会进行传播，直至达到用户代码。  
  
 这些操作保证了在启用传播的情况下，用户跟踪将出现在相同的活动中。 但是，这不保证 ServiceModel 跟踪。 仅当 ServiceModel 跟踪处理是在设置用户代码活动的线程中执行时，这些跟踪才会出现在用户代码活动中。  
  
 一般而言，在以下位置可以观察到 ServiceModel 跟踪：  
  
-   如果禁用 ServiceModel 跟踪，则发出的所有跟踪都将出现在用户活动中。 如果服务器和客户端上都启用传播，则这些跟踪将在同一个活动中。  
  
-   如果启用了 ServiceModel 跟踪，但禁用了 ActivityTracing，并且服务器和客户端都启用传播，则用户跟踪将出现在同一个活动中。 ServiceModel 跟踪出现在默认的 0000 活动中，除非这些跟踪发生在与最初设置该活动的用户代码处理相同的线程中。  
  
-   如果启用了 ServiceModel 跟踪和 ActivityTracing，则用户跟踪将出现在用户定义的活动中，而 ServiceModel 跟踪则出现在 ServiceModel 定义的活动中。 传播在 ServiceModel 级别发生。
