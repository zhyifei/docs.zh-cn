---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804654"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load 不会删除符号属性

|   |   |
|---|---|
|详细信息|当在工作流设计器中面向 .NET Framework 4.5，并使用 <xref:System.Activities.Presentation.WorkflowDesigner.Load> 方法加载重新托管的 3.5 工作流时，保存该工作流的同时将引发 <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name>。|
|建议|此 bug 仅当在工作流设计器中面向 .NET Framework 4.5 时才显示，因此可通过将 <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> 设为 4.0 .NET Framework 进行解决。或者，可使用 <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> 方法而非 <xref:System.Activities.Presentation.WorkflowDesigner.Load> 方法加载工作流来避免此问题。|
|范围|主要|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

