---
title: 实例锁定异常操作
ms.date: 03/30/2017
ms.assetid: 164a5419-315c-4987-ad72-54cbdb88d402
ms.openlocfilehash: 6146316d9fd09d9928642c0d98e3852ae1331b2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517278"
---
# <a name="instance-locked-exception-action"></a>实例锁定异常操作
利用 SQL 工作流实例存储的 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> 属性，可以指定当 SQL 持久性提供程序收到 <xref:System.Runtime.DurableInstancing.InstanceLockedException> 时应采取什么操作。 当持久性提供程序尝试锁定当前已由另一个服务主机锁定的工作流服务实例时，将收到此异常。 此属性的值有 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>、<xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> 和 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>。 默认值为 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>。 以下列表对这三个选项进行了说明：  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>。 服务主机不会尝试锁定工作流服务实例，并传递<xref:System.Runtime.DurableInstancing.InstanceLockedException>给调用方。  如果你的工作流在内存中保持的一段时间，超过 60 秒，则使用<xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>因为重试。 默认值为 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>。  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry>。 服务主机将以线性间隔在重试尝试之间重新尝试锁定工作流服务实例，并在序列结尾将 <xref:System.Runtime.DurableInstancing.InstanceLockedException> 传递给调用方。 如果工作流在内存中将停留约 5-60 秒，并且消息分批到达（其中，消息更可能发送给相同主机上的相同实例，以便处理所有消息，然后再卸载工作流），则使用 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> 可实现最佳延迟并且不会浪费资源。  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>。 服务主机将以指数回退间隔在重试之间重新尝试锁定工作流服务实例，并在序列结尾将异常传递给调用方。 如果您的工作流在内存中停留的时间很短（少于 5 秒），或者网络场很大并且另一个消息传递到同一主机的机会不是很高，则使用 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry> 可实现最佳延迟。  
  
 实例锁定异常操作功能支持以下方案。 在所有方案中，如果将 SqlWorkflowInstanceStore 的 instanceLockedExceptionAction 属性设置为 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> 或 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>，主机会定期透明地重试获取对实例的锁定。  
  
1.  **启用正常关机和应用程序域的重叠回收。** 假设**AppDomain**与服务主机正在运行工作流服务实例正在回收新**AppDomain**时，将启动以处理新旧的并行请求**AppDomain**正常关闭。 此关闭将等待一段时间，直到工作流服务实例空闲为止，然后将保存并卸载这些实例。 在新的主机的任何尝试**AppDomain**尝试锁定该实例将导致<xref:System.Runtime.DurableInstancing.InstanceLockedException>。  
  
2.  **在同类服务器场中水平扩展持久性工作流。** 假定服务器场中正在运行工作流实例的某一节点崩溃，并且工作流主机无法移除对其正在运行的实例的锁定。 当场中的另一节点上运行的服务主机接收到有关该工作流实例的消息时，它会尝试获取对这些实例的锁定，并且将接收到 <xref:System.Runtime.DurableInstancing.InstanceLockedException>。 该锁定将在一段时间后过期，这是因为原本应续订锁定的主机已不再存在。  
  
     **在同类服务器场中水平扩展持久性工作流。**  假设你想要横向扩展使用后面 NLB （网络负载平衡器） 的多个主机的持久工作流时，服务器场中的一个节点上运行的工作流主机加载工作流实例正在处理的消息，并实例到下一条消息路由到在另一个节点运行，因为 NLB 没有路由算法将消息传递到已运行的实例的主机的主机。 接收到此消息后，第二个主机尝试加载工作流实例，并接收到 <xref:System.Runtime.DurableInstancing.InstanceLockedException>，这是因为第一个主机已锁定该实例。 第一个主机在处理完第一条消息后，将解除对该实例的锁定，第二个主机将在下次重试时获取锁定，然后加载该实例，并处理第二条消息。
