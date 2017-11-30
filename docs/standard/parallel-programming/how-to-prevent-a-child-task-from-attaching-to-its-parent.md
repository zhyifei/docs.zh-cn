---
title: "如何：防止子任务附加到其父任务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4717e3a077648d9db51fe39228209617b384bd0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a><span data-ttu-id="024d8-102">如何：防止子任务附加到其父任务</span><span class="sxs-lookup"><span data-stu-id="024d8-102">How to: Prevent a Child Task from Attaching to its Parent</span></span>
<span data-ttu-id="024d8-103">本文档演示如何阻止子任务附加到父任务。</span><span class="sxs-lookup"><span data-stu-id="024d8-103">This document demonstrates how to prevent a child task from attaching to the parent task.</span></span> <span data-ttu-id="024d8-104">在调用由第三方编写的也使用任务的组件时，阻止子任务附加到其父级是有用的。</span><span class="sxs-lookup"><span data-stu-id="024d8-104">Preventing a child task from attaching to its parent is useful when you call a component that is written by a third party and that also uses tasks.</span></span> <span data-ttu-id="024d8-105">例如，使用 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> 选项创建 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601> 对象的第三方组件，如果长时间运行或引发未经处理的异常，可能会导致代码中出现问题。</span><span class="sxs-lookup"><span data-stu-id="024d8-105">For example, a third-party component that uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> option to create a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object can cause problems in your code if it is long-running or throws an unhandled exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="024d8-106">示例</span><span class="sxs-lookup"><span data-stu-id="024d8-106">Example</span></span>  
 <span data-ttu-id="024d8-107">下面的示例对使用默认选项的效果与阻止子任务附加到其父级的效果进行比较。</span><span class="sxs-lookup"><span data-stu-id="024d8-107">The following example compares the effects of using the default options to the effects of preventing a child task from attaching to the parent.</span></span> <span data-ttu-id="024d8-108">示例创建了一个 <xref:System.Threading.Tasks.Task> 对象，该对象可调入同时使用 <xref:System.Threading.Tasks.Task> 对象的第三方库。</span><span class="sxs-lookup"><span data-stu-id="024d8-108">The example creates a <xref:System.Threading.Tasks.Task> object that calls into a third-party library that also uses a <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="024d8-109">第三方库使用 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> 选项创建 <xref:System.Threading.Tasks.Task> 对象。</span><span class="sxs-lookup"><span data-stu-id="024d8-109">The third-party library uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> option to create the <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="024d8-110">应用程序使用 <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> 选项创建父任务。</span><span class="sxs-lookup"><span data-stu-id="024d8-110">The application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option to create the parent task.</span></span> <span data-ttu-id="024d8-111">该选项指示运行时移除子任务中的 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> 规范。</span><span class="sxs-lookup"><span data-stu-id="024d8-111">This option instructs the runtime to remove the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specification in child tasks.</span></span>  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 <span data-ttu-id="024d8-112">因为父任务只有在所有子任务完成后才会完成，所以长时间运行的子任务会让整个应用程序执行得非常缓慢。</span><span class="sxs-lookup"><span data-stu-id="024d8-112">Because a parent task does not finish until all child tasks finish, a long-running child task can cause the overall application to perform poorly.</span></span> <span data-ttu-id="024d8-113">在此示例中，当应用程序使用默认选项创建父任务时，子任务必须在父任务完成之前完成。</span><span class="sxs-lookup"><span data-stu-id="024d8-113">In this example, when the application uses the default options to create the parent task, the child task must finish before the parent task finishes.</span></span> <span data-ttu-id="024d8-114">当应用程序使用 <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> 选项时，子任务未附加到父任务。</span><span class="sxs-lookup"><span data-stu-id="024d8-114">When the application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option, the child is not attached to the parent.</span></span> <span data-ttu-id="024d8-115">因此，应用程序可以在父任务完成之后且必须等待子任务完成之前执行其他工作。</span><span class="sxs-lookup"><span data-stu-id="024d8-115">Therefore, the application can perform additional work after the parent task finishes and before it must wait for the child task to finish.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="024d8-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="024d8-116">Compiling the Code</span></span>  
 <span data-ttu-id="024d8-117">复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `DenyChildAttach.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `DenyChildAttach.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="024d8-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DenyChildAttach.cs` (`DenyChildAttach.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="024d8-118">**csc.exe DenyChildAttach.cs**</span><span class="sxs-lookup"><span data-stu-id="024d8-118">**csc.exe DenyChildAttach.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="024d8-119">**vbc.exe DenyChildAttach.vb**</span><span class="sxs-lookup"><span data-stu-id="024d8-119">**vbc.exe DenyChildAttach.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="024d8-120">可靠编程</span><span class="sxs-lookup"><span data-stu-id="024d8-120">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="024d8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="024d8-121">See Also</span></span>  
 [<span data-ttu-id="024d8-122">基于任务的异步编程</span><span class="sxs-lookup"><span data-stu-id="024d8-122">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
