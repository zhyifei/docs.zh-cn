---
title: 如何：处理因数据绑定而发生的错误和异常
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 14326d793be3ee71022a7a1e7398b9af469aab10
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592450"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="10543-102">如何：处理因数据绑定而发生的错误和异常</span><span class="sxs-lookup"><span data-stu-id="10543-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="10543-103">将基础业务对象绑定到控件时，此类对象上时常发生异常和错误。</span><span class="sxs-lookup"><span data-stu-id="10543-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="10543-104">可以截获这些错误和异常，然后通过为特定的 <xref:System.Windows.Forms.Binding>、<xref:System.Windows.Forms.BindingSource> 或 <xref:System.Windows.Forms.CurrencyManager> 组件处理 <xref:System.Windows.Forms.Binding.BindingComplete> 事件恢复错误信息或将此信息传递至用户。</span><span class="sxs-lookup"><span data-stu-id="10543-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10543-105">示例</span><span class="sxs-lookup"><span data-stu-id="10543-105">Example</span></span>  
 <span data-ttu-id="10543-106">此代码示例演示了如何处理数据绑定操作过程中发生的错误和异常。</span><span class="sxs-lookup"><span data-stu-id="10543-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="10543-107">此示例演示了如何通过处理 <xref:System.Windows.Forms.Binding> 对象的 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> 事件截获错误。</span><span class="sxs-lookup"><span data-stu-id="10543-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="10543-108">为了通过处理此事件来截获错误和异常，必须启用绑定的格式化。</span><span class="sxs-lookup"><span data-stu-id="10543-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="10543-109">可在构造绑定或将其添加到绑定集合时，或通过将 <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> 属性设置为 `true`，来启用格式化。</span><span class="sxs-lookup"><span data-stu-id="10543-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="10543-110">当代码正在运行，且为部件名输入的字符串为空或为部件号输入的值小于 100 时，将显示一个消息框。</span><span class="sxs-lookup"><span data-stu-id="10543-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="10543-111">这是为这些文本框绑定处理 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> 事件产生的结果。</span><span class="sxs-lookup"><span data-stu-id="10543-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10543-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="10543-112">Compiling the Code</span></span>  
 <span data-ttu-id="10543-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="10543-113">This example requires:</span></span>  
  
- <span data-ttu-id="10543-114">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="10543-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10543-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="10543-115">See also</span></span>

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [<span data-ttu-id="10543-116">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="10543-116">BindingSource Component</span></span>](bindingsource-component.md)
