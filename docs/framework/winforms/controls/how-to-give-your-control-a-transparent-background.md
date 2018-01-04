---
title: "如何：使控件拥有透明背景"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab2a8562401561cfb2a54d4630e32bf7527da10d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="bcb82-102">如何：使控件拥有透明背景</span><span class="sxs-lookup"><span data-stu-id="bcb82-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="bcb82-103">在早期版本的.NET Framework 中，如果事先未在窗体的构造函数中设置 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法，控件将不支持设置透明背景色。</span><span class="sxs-lookup"><span data-stu-id="bcb82-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="bcb82-104">在当前的框架版本中，可以在设计时在“属性” <xref:System.Drawing.Color.Transparent%2A>**窗口中或在窗体构造函数的代码中将背景色设置为** 。</span><span class="sxs-lookup"><span data-stu-id="bcb82-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcb82-105">Windows 窗体控件不支持真正的透明。</span><span class="sxs-lookup"><span data-stu-id="bcb82-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="bcb82-106">透明 Windows 窗体控件的背景由其父级绘制。</span><span class="sxs-lookup"><span data-stu-id="bcb82-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcb82-107">即使将 <xref:System.Windows.Controls.Button> 属性设置为 <xref:System.Windows.Forms.ButtonBase.BackColor%2A> ， <xref:System.Drawing.Color.Transparent%2A>控件也不支持透明背景色。</span><span class="sxs-lookup"><span data-stu-id="bcb82-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="bcb82-108">使控件拥有透明背景色</span><span class="sxs-lookup"><span data-stu-id="bcb82-108">To give your control a transparent backcolor</span></span>  
  
-   <span data-ttu-id="bcb82-109">在“属性”窗口中，选择 <xref:System.Windows.Forms.ButtonBase.BackColor%2A> 属性并将其设置为 <xref:System.Drawing.Color.Transparent%2A></span><span class="sxs-lookup"><span data-stu-id="bcb82-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to <xref:System.Drawing.Color.Transparent%2A></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb82-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcb82-110">See Also</span></span>  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [<span data-ttu-id="bcb82-111">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="bcb82-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="bcb82-112">使用托管图形类</span><span class="sxs-lookup"><span data-stu-id="bcb82-112">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [<span data-ttu-id="bcb82-113">如何：绘制不透明和半透明的直线</span><span class="sxs-lookup"><span data-stu-id="bcb82-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
