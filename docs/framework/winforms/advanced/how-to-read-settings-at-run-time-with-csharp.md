---
title: 如何：在运行时读取设置C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d798b40e5e337ea7652c8e82cb7fa860a87528b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521746"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="76f3e-102">如何：在运行时读取设置C#</span><span class="sxs-lookup"><span data-stu-id="76f3e-102">How To: Read Settings at Run Time With C#</span></span> #
<span data-ttu-id="76f3e-103">可以通过“属性”对象在运行时读取应用程序范围和用户范围的设置。</span><span class="sxs-lookup"><span data-stu-id="76f3e-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="76f3e-104">“属性”对象通过 Properties.Settings.Default 成员公开项目的所有默认设置。</span><span class="sxs-lookup"><span data-stu-id="76f3e-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
### <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="76f3e-105">在运行时读取设置 (C#)</span><span class="sxs-lookup"><span data-stu-id="76f3e-105">To Read Settings at Run Time with C#</span></span>  
  
-   <span data-ttu-id="76f3e-106">请通过 Properties.Settings.Default 成员访问相应的设置。</span><span class="sxs-lookup"><span data-stu-id="76f3e-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="76f3e-107">下面的示例演示如何将名为 `myColor` 的设置分配给 BackColor 属性。</span><span class="sxs-lookup"><span data-stu-id="76f3e-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="76f3e-108">这要求你在之前已创建包含名为 `myColor` 的设置（其类型为 `System.Drawing.Color`）的设置文件。</span><span class="sxs-lookup"><span data-stu-id="76f3e-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="76f3e-109">有关创建设置文件的信息，请参阅[How To:在设计时创建新的设置](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="76f3e-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="76f3e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="76f3e-110">See also</span></span>
- [<span data-ttu-id="76f3e-111">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="76f3e-111">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [<span data-ttu-id="76f3e-112">如何：在运行时编写用户设置C#</span><span class="sxs-lookup"><span data-stu-id="76f3e-112">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="76f3e-113">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="76f3e-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
