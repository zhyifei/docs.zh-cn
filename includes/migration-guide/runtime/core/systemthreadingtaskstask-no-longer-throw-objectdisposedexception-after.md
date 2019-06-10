---
ms.openlocfilehash: ab2907b05bff409fed9a370d5cbebbf3d1575d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379534"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>释放对象后，System.Threading.Tasks.Task 不再引发 ObjectDisposedException

|   |   |
|---|---|
|详细信息|除 <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle> 外，<xref:System.Threading.Tasks.Task?displayProperty=name> 方法在处置对象后不再引发 <xref:System.ObjectDisposedException?displayProperty=name> 异常。此更改支持使用缓存任务。 例如，方法会返回一个缓存任务来表示已完成的操作，而不是分配新任务。 在以前的 .NET Framework 版本中无法执行此操作，因为任务的任何使用者都可以处置它（呈现为不可用）。|
|建议|请注意，如果释放对象，Task 方法可能不再引发 <xref:System.ObjectDisposedException?displayProperty=name>。 如果某个应用依靠此异常了解任务是否已释放，应对其进行更新以使用 <xref:System.Threading.Tasks.Task.Status> 显式检查任务状态。|
|范围|次要|
|版本|4.5|
|类型|运行时|
