---
title: ErrorProvider 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 485e7a17073d72618b9599113179cddde748e697
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181176"
---
# <a name="errorprovider-component-overview-windows-forms"></a><span data-ttu-id="12fcf-102">ErrorProvider 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="12fcf-102">ErrorProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="12fcf-103">Windows 窗体[ErrorProvider](errorprovider-component-windows-forms.md)组件用来验证窗体或控件的用户输入。</span><span class="sxs-lookup"><span data-stu-id="12fcf-103">The Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) component is used to validate user input on a form or control.</span></span> <span data-ttu-id="12fcf-104">它通常使用与验证窗体上的用户输入或显示在数据集中的错误。</span><span class="sxs-lookup"><span data-stu-id="12fcf-104">It is typically used in conjunction with validating user input on a form, or displaying errors within a dataset.</span></span> <span data-ttu-id="12fcf-105">错误提供程序是更好的选择与在消息框中，显示一条错误消息，因为一旦关闭消息框，则错误消息不再可见。</span><span class="sxs-lookup"><span data-stu-id="12fcf-105">An error provider is a better alternative than displaying an error message in a message box, because once a message box is dismissed, the error message is no longer visible.</span></span> <span data-ttu-id="12fcf-106"><xref:System.Windows.Forms.ErrorProvider>组件均显示一个错误图标 (![ErrorProvider 图标](./media/vberrorprovidericon.gif "vbErrorProviderIcon")) 相关的控件，例如文本框; 当用户鼠标指针悬停旁边错误图标工具提示出现，显示错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="12fcf-106">The <xref:System.Windows.Forms.ErrorProvider> component displays an error icon (![ErrorProvider icon](./media/vberrorprovidericon.gif "vbErrorProviderIcon")) next to the relevant control, such as a text box; when the user positions the mouse pointer over the error icon, a ToolTip appears, showing the error message string.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="12fcf-107">键属性</span><span class="sxs-lookup"><span data-stu-id="12fcf-107">Key Properties</span></span>  
 <span data-ttu-id="12fcf-108"><xref:System.Windows.Forms.ErrorProvider>组件的主要属性有<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>， <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>，和<xref:System.Windows.Forms.ErrorProvider.Icon%2A>。</span><span class="sxs-lookup"><span data-stu-id="12fcf-108">The <xref:System.Windows.Forms.ErrorProvider> component's key properties are <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, and <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.</span></span> <span data-ttu-id="12fcf-109">使用时<xref:System.Windows.Forms.ErrorProvider>组件与数据绑定控件<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>属性必须设置为适当的容器 （通常是 Windows 窗体） 中要在窗体上显示一个错误图标的组件的顺序。</span><span class="sxs-lookup"><span data-stu-id="12fcf-109">When using <xref:System.Windows.Forms.ErrorProvider> component with data-bound controls, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property must be set to the appropriate container (usually the Windows Form) in order for the component to display an error icon on the form.</span></span> <span data-ttu-id="12fcf-110">在设计器中，添加组件时<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>属性设置为包含窗体; 如果在代码中添加控件，则必须将其自己。</span><span class="sxs-lookup"><span data-stu-id="12fcf-110">When the component is added in the designer, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property is set to the containing form; if you add the control in code, you must set it yourself.</span></span>  
  
 <span data-ttu-id="12fcf-111"><xref:System.Windows.Forms.ErrorProvider.Icon%2A>属性可以设置为自定义错误图标而不是默认值。</span><span class="sxs-lookup"><span data-stu-id="12fcf-111">The <xref:System.Windows.Forms.ErrorProvider.Icon%2A> property can be set to a custom error icon instead of the default.</span></span> <span data-ttu-id="12fcf-112">当<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>属性设置，<xref:System.Windows.Forms.ErrorProvider>组件可以显示的数据集的错误消息。</span><span class="sxs-lookup"><span data-stu-id="12fcf-112">When the <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> property is set, the <xref:System.Windows.Forms.ErrorProvider> component can display error messages for a dataset.</span></span> <span data-ttu-id="12fcf-113">关键方法<xref:System.Windows.Forms.ErrorProvider>组件是<xref:System.Windows.Forms.ErrorProvider.SetError%2A>方法，用于指定错误消息字符串以及应显示错误图标的位置。</span><span class="sxs-lookup"><span data-stu-id="12fcf-113">The key method of the <xref:System.Windows.Forms.ErrorProvider> component is the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method, which specifies the error message string and where the error icon should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12fcf-114"><xref:System.Windows.Forms.ErrorProvider>组件没有可访问性客户端提供的内置支持。</span><span class="sxs-lookup"><span data-stu-id="12fcf-114">The <xref:System.Windows.Forms.ErrorProvider> component does not provide built-in support for accessibility clients.</span></span> <span data-ttu-id="12fcf-115">若要使你的应用程序时使用此组件可访问，必须提供其他可访问的反馈机制。</span><span class="sxs-lookup"><span data-stu-id="12fcf-115">To make your application accessible when using this component, you must provide an additional, accessible feedback mechanism.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fcf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="12fcf-116">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider>
- [<span data-ttu-id="12fcf-117">如何：在一个数据集中使用 Windows 窗体 ErrorProvider 组件查看错误</span><span class="sxs-lookup"><span data-stu-id="12fcf-117">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [<span data-ttu-id="12fcf-118">如何：对于表格验证使用 Windows 窗体 ErrorProvider 组件显示错误图标</span><span class="sxs-lookup"><span data-stu-id="12fcf-118">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)
