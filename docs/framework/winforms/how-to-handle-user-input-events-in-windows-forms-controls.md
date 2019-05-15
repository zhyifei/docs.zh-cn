---
title: 如何：在 Windows 窗体控件中处理用户输入事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: ae230f22c929be39ea00eafe378c6910c4a9d35f
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592075"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="d3de4-102">如何：在 Windows 窗体控件中处理用户输入事件</span><span class="sxs-lookup"><span data-stu-id="d3de4-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="d3de4-103">此示例演示如何处理大多数键盘、鼠标、焦点和 Windows 窗体控件中可能会发生的验证事件。</span><span class="sxs-lookup"><span data-stu-id="d3de4-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="d3de4-104">命名为 `TextBoxInput` 的文本框在其具有焦点时接收事件，有关每个事件的信息将以事件发生的顺序写入被命名为 `TextBoxOutput` 的文本框中。</span><span class="sxs-lookup"><span data-stu-id="d3de4-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="d3de4-105">该应用程序还包括一组复选框，可用于筛选要报告的事件。</span><span class="sxs-lookup"><span data-stu-id="d3de4-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3de4-106">示例</span><span class="sxs-lookup"><span data-stu-id="d3de4-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d3de4-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="d3de4-107">Compiling the Code</span></span>  
 <span data-ttu-id="d3de4-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d3de4-108">This example requires:</span></span>  
  
- <span data-ttu-id="d3de4-109">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d3de4-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3de4-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3de4-110">See also</span></span>

- [<span data-ttu-id="d3de4-111">Windows 窗体中的用户输入</span><span class="sxs-lookup"><span data-stu-id="d3de4-111">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
