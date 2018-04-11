---
title: 未指定启动窗体
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdffc182ee66497d68aafb7dc37cfef75b4d2e9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="0bdd8-102">未指定启动窗体</span><span class="sxs-lookup"><span data-stu-id="0bdd8-102">A startup form has not been specified</span></span>
<span data-ttu-id="0bdd8-103">应用程序使用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>类，但未指定启动窗体。</span><span class="sxs-lookup"><span data-stu-id="0bdd8-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="0bdd8-104">发生这种情况**启用应用程序框架**项目设计器中选中复选框，但**启动窗体**未指定。</span><span class="sxs-lookup"><span data-stu-id="0bdd8-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="0bdd8-105">有关详细信息，请参阅 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)（应用程序页、项目设计器 (Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="0bdd8-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0bdd8-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0bdd8-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="0bdd8-107">指定应用程序的启动对象。</span><span class="sxs-lookup"><span data-stu-id="0bdd8-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="0bdd8-108">有关详细信息，请参阅 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)（应用程序页、项目设计器 (Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="0bdd8-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="0bdd8-109">重写<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>方法以设置<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>启动窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="0bdd8-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdd8-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bdd8-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [<span data-ttu-id="0bdd8-111">Visual Basic 应用程序模型概述</span><span class="sxs-lookup"><span data-stu-id="0bdd8-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
