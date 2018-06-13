---
title: 如何：创建自定义持久性参与者
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: fcd96e41d8fc7b36f9dff5f10e9bc2d9034d79b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517236"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>如何：创建自定义持久性参与者
下列过程包含持久性参与者的创建步骤。 请参阅[参与持久性](http://go.microsoft.com/fwlink/?LinkID=177735)示例和[存储扩展性](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)示例实现的持久性参与者的主题。  
  
1.  创建一个派生自 <xref:System.Activities.Persistence.PersistenceParticipant> 或 <xref:System.Activities.Persistence.PersistenceIOParticipant> 类的类。 PersistenceIOParticipant 类还提供与 PersistenceParticipant 类除了能够参与 I/O 操作相同的扩展点。 请完成以下一个或多个步骤。  
  
2.  实现 <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> 方法。 **CollectValues**方法具有两个字典参数，一个用于存储读/写值，另一个用于存储只写值 （稍后在查询中使用）。 在此方法中，应使用特定于持久性参与者的数据填充这些字典。 每个字典都包含值的名称和值自身，前者作为键，后者作为 <xref:System.Runtime.DurableInstancing.InstanceValue> 对象。  
  
     ReadWriteValues 字典中的值打包为**InstanceValue**对象。 只写字典中的值打包为**InstanceValue** InstanceValueOptions.Optional 和 InstanceValueOption.WriteOnly 的组的对象。 每个**InstanceValue**由**CollectValues**所有持久性参与者实现必须具有唯一的名称。  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3.  实现 <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 方法。 **MapValues**方法采用类似于参数的两个参数， **CollectValues**方法接收。 在收集的所有值**CollectValues**阶段传递通过这些字典参数。 通过添加的新值**MapValues**阶段添加到只写值。  只写字典用于向外部源提供不直接与实例值相关联的数据。 实现提供的每个值**MapValues**所有持久性参与者的方法必须具有唯一的名称。  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 方法提供 <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> 不实现的功能，因为它允许由另一个持久性参与者提供另一个值的依赖项，该参与者尚未经过 <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> 的处理。  
  
4.  实现**PublishValues**方法。 **PublishValues**方法接收一个包含从持久性存储区中加载的所有值的字典。  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5.  实现**BeginOnSave**如果参与者是持久性 I/O 参与者的方法。 在执行保存操作期间，将调用此方法。 在此方法中，你应执行 I/O 附加持久保存 （保存） 工作流实例。  如果主机正将事务用于相应的持久性命令，则会在 Transaction.Current 中提供相同事务。  此外，持久性 IO 参与者可公布事务一致性需求，在这种情况中，主机将为持久性段创建一个事务（如果不会在其他情况下使用该事务）。  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  实现**BeginOnLoad**如果参与者是持久性 I/O 参与者的方法。 在执行加载操作期间，将调用此方法。 在此方法中，你应执行的工作流实例加载到的 I/O 附加。 如果主机正将事务用于相应的持久性命令，则会在 Transaction.Current 中提供相同事务。 此外，持久性 I/O 参与者可公布事务一致性要求，如果将未使用一种否则是用例主机创建一个事务为持久性段。  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
