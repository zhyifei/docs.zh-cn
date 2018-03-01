---
title: "ErrorProvider 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 589735156ad4d6d639c2449d6bd693e2b3a32d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a><span data-ttu-id="847b9-102">ErrorProvider 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="847b9-102">ErrorProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="847b9-103">Windows 窗体[ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md)组件用来验证窗体或控件上的用户输入。</span><span class="sxs-lookup"><span data-stu-id="847b9-103">The Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) component is used to validate user input on a form or control.</span></span> <span data-ttu-id="847b9-104">它通常是与验证窗体上的用户输入或显示在数据集中的错误结合使用。</span><span class="sxs-lookup"><span data-stu-id="847b9-104">It is typically used in conjunction with validating user input on a form, or displaying errors within a dataset.</span></span> <span data-ttu-id="847b9-105">错误提供程序是更好的选择，比在消息框中，显示一条错误消息，因为后关闭消息框，则错误消息不再可见。</span><span class="sxs-lookup"><span data-stu-id="847b9-105">An error provider is a better alternative than displaying an error message in a message box, because once a message box is dismissed, the error message is no longer visible.</span></span> <span data-ttu-id="847b9-106"><xref:System.Windows.Forms.ErrorProvider>组件显示错误图标 (![ErrorProvider 图标](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) 相关的控件，如文本框; 当用户鼠标指针悬停旁边显示错误图标，工具提示，显示错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="847b9-106">The <xref:System.Windows.Forms.ErrorProvider> component displays an error icon (![ErrorProvider icon](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) next to the relevant control, such as a text box; when the user positions the mouse pointer over the error icon, a ToolTip appears, showing the error message string.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="847b9-107">键属性</span><span class="sxs-lookup"><span data-stu-id="847b9-107">Key Properties</span></span>  
 <span data-ttu-id="847b9-108"><xref:System.Windows.Forms.ErrorProvider>组件的主要属性包括<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>， <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>，和<xref:System.Windows.Forms.ErrorProvider.Icon%2A>。</span><span class="sxs-lookup"><span data-stu-id="847b9-108">The <xref:System.Windows.Forms.ErrorProvider> component's key properties are <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, and <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.</span></span> <span data-ttu-id="847b9-109">使用时<xref:System.Windows.Forms.ErrorProvider>组件与数据绑定控件<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>顺序以窗体上显示错误图标组件的情况下，属性必须设置为适当的容器 （通常是 Windows 窗体）。</span><span class="sxs-lookup"><span data-stu-id="847b9-109">When using <xref:System.Windows.Forms.ErrorProvider> component with data-bound controls, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property must be set to the appropriate container (usually the Windows Form) in order for the component to display an error icon on the form.</span></span> <span data-ttu-id="847b9-110">当在设计器中，将该组件添加<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>属性设置为包含窗体; 如果你在代码中添加控件，必须将它自己。</span><span class="sxs-lookup"><span data-stu-id="847b9-110">When the component is added in the designer, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property is set to the containing form; if you add the control in code, you must set it yourself.</span></span>  
  
 <span data-ttu-id="847b9-111"><xref:System.Windows.Forms.ErrorProvider.Icon%2A>属性可以设置为一个自定义错误图标而不是默认值。</span><span class="sxs-lookup"><span data-stu-id="847b9-111">The <xref:System.Windows.Forms.ErrorProvider.Icon%2A> property can be set to a custom error icon instead of the default.</span></span> <span data-ttu-id="847b9-112">当<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>设置属性，<xref:System.Windows.Forms.ErrorProvider>组件可以显示为数据集的错误消息。</span><span class="sxs-lookup"><span data-stu-id="847b9-112">When the <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> property is set, the <xref:System.Windows.Forms.ErrorProvider> component can display error messages for a dataset.</span></span> <span data-ttu-id="847b9-113">关键方法<xref:System.Windows.Forms.ErrorProvider>组件是<xref:System.Windows.Forms.ErrorProvider.SetError%2A>方法，它指定的错误消息字符串，并应显示错误图标的位置。</span><span class="sxs-lookup"><span data-stu-id="847b9-113">The key method of the <xref:System.Windows.Forms.ErrorProvider> component is the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method, which specifies the error message string and where the error icon should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="847b9-114"><xref:System.Windows.Forms.ErrorProvider>组件不提供辅助功能客户端的内置支持。</span><span class="sxs-lookup"><span data-stu-id="847b9-114">The <xref:System.Windows.Forms.ErrorProvider> component does not provide built-in support for accessibility clients.</span></span> <span data-ttu-id="847b9-115">若要使用此组件时，使你的应用程序可访问，必须提供其他可访问的反馈机制。</span><span class="sxs-lookup"><span data-stu-id="847b9-115">To make your application accessible when using this component, you must provide an additional, accessible feedback mechanism.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="847b9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="847b9-116">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider>  
 [<span data-ttu-id="847b9-117">如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误</span><span class="sxs-lookup"><span data-stu-id="847b9-117">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [<span data-ttu-id="847b9-118">如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标</span><span class="sxs-lookup"><span data-stu-id="847b9-118">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
