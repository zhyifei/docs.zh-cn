---
title: 调试工作流
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 17cee1f1b509e777edd3f08c55d473d768b19b55
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463533"
---
# <a name="debugging-workflows"></a>调试工作流
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]提供多个用于从开发环境调试运行的工作流的选项。 可以在设计器、XAML 和代码中调试工作流。  
  
## <a name="debugging-in-the-workflow-designer"></a>在工作流设计器中调试  
 可以通过突出显示活动并按工作流设计器中的活动上设置断点**F9**或通过使用活动的上下文菜单。 然后，当工作流宿主在调试模式下运行时将中断工作流的执行。 在下面的屏幕快照中，工作流执行在断点处暂停。 有关详细信息，请参阅[与工作流设计器调试工作流](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer)。  
  
## <a name="debugging-in-xaml"></a>在 XAML 中调试  
 如果在设计器中某个工作流已在断点处暂停，则还可以在 XAML 中调试该工作流。 若要在 XAML 中查看执行点，请选择**XAML 视图**暂停工作流执行时在工作流设计器中。 通过从解决方案资源管理器重新打开工作流可以将调试切换回设计器。 有关详细信息，请参阅[如何： 使用工作流设计器调试 XAML](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer)。  
  
## <a name="debugging-in-code"></a>在代码中调试  
 也可以在 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中使用代码断点，其使用方式与在其他命令性应用程序中相同。 单击左边的距的代码窗格，以创建一个代码断点，或按**F9**的光标位置处放置一个断点。  
  
## <a name="attaching-to-a-workflow-process"></a>附加到工作流过程  
 工作流调试还支持使用 Visual Studio 的基础结构附加到某个过程。 这使工作流创作者能够调试在另一个宿主环境（如 Internet 信息服务 (IIS) 7.0）中运行的工作流。  
  
## <a name="remote-debugging"></a>Remote Debugging  
 Windows Workflow Foundation (WF) 进行远程调试的函数与其他 Visual Studio 组件远程调试相同。 有关使用远程调试的信息，请参阅[如何： 启用远程调试](https://go.microsoft.com/fwlink/?LinkId=196257)。  
  
> [!NOTE]
>  如果工作流应用程序针对 x86 体系结构并位于运行 64 位操作系统的计算机上远程调试将不工作，除非在远程计算机上安装 Visual Studio 或工作流应用程序的目标更改为**任何 CPU**。  
  
## <a name="extending-the-workflow-debugging-service"></a>扩展工作流调试服务  
 工作流调试器服务现在以公共方式使用，可以使用该服务创建自定义应用程序，如在重新承载的设计器中进行监视、模拟和调试。 有关详细信息，请参见<xref:System.Activities.Presentation.Debug.DebuggerService>主题。
