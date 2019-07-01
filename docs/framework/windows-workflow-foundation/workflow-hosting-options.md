---
title: 工作流托管选项
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: b0cd9748c28cd6206e1fedffc5772b2849462dba
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487366"
---
# <a name="workflow-hosting-options"></a>工作流托管选项
大多数 Windows Workflow Foundation (WF) 示例使用控制台应用程序中承载的工作流，但这不是实际的工作流的实际方案。 实际业务应用程序中的工作流将由开发人员版或的服务器应用程序，例如 IIS 7.0 或 AppFabric 承载在恒定进程中 — 创作 Windows 服务。 这些方法之间的区别如下。  
  
## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>用配有 Windows AppFabric 的 IIS 承载工作流  
 用配有 AppFabric 的 IIS 是承载工作流的首选方法。 用 AppFabric 来承载工作流的应用程序是 Windows Activation Service，它解除了仅通过 IIS 对 HTTP 的依赖。  
  
## <a name="hosting-workflows-in-iis-alone"></a>仅用 IIS 来承载工作流  
 不建议使用单独的 IIS 7.0，因为有管理和监控工具可使用 AppFabric，便于您正在运行的应用程序的维护。 仅应在迁移到 AppFabric 的基础结构问题是否单独的 IIS 7.0 中托管工作流。  
  
> [!WARNING]
>  IIS 7.0 出于各种原因而定期回收应用程序池。 当应用程序池被回收时，IIS 即停止接受发给旧应用程序池的消息，并实例化一个新的应用程序池以接受新请求。 如果工作流发送响应后继续运行，IIS 7.0 将无法识别的工作负荷，并且可能会回收托管的应用程序池。 如果发生这种情况，将中止工作流，并跟踪服务则记录[1004-WorkflowInstanceAborted](1004-workflowinstanceaborted.md)与 Reason 字段为空的消息。  
>   
>  如果使用了持久化机制，则主机必须显式地从上一个持久化点重启被中止的实例。  
>   
>  如果使用了 AppFabric，则工作流管理服务最终将从上次成功持久化的点恢复工作流（如果使用了持久化机制）。 如果未使用持久化机制，则该工作流执行非“请求/响应”模式的操作，当工作流中止时，数据也将丢失。  
  
## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>在自定义 Windows 服务中承载工作流  
 若要创建自定义工作流服务来承载工作流，要求开发人员复制 AppFabric 自带的许多功能，但允许通过自定义功能实现更大的灵活性。 仅当 AppFabric 经证不合适时，才应考虑这一选项。
