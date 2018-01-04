---
title: "使用应用程序设置和用户设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 310fcad07ce7cf541312ff83e41d7e5fc2643898
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="e830c-102">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="e830c-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="e830c-103">从.NET Framework 2.0 开始，可以创建和访问应用程序执行会话之间保留的值。</span><span class="sxs-lookup"><span data-stu-id="e830c-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="e830c-104">这些值称为*设置*。</span><span class="sxs-lookup"><span data-stu-id="e830c-104">These values are called *settings*.</span></span> <span data-ttu-id="e830c-105">设置可以表示用户首选项，或者有价值信息的应用程序需要使用。</span><span class="sxs-lookup"><span data-stu-id="e830c-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="e830c-106">例如，你可能会创建一系列存储应用程序的配色方案的用户首选项的设置。</span><span class="sxs-lookup"><span data-stu-id="e830c-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="e830c-107">或者，你可能会存储指定你的应用程序使用的数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="e830c-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="e830c-108">设置允许你同时保留对外部代码，并创建存储的单个用户的首选项的配置文件的应用程序至关重要的信息。</span><span class="sxs-lookup"><span data-stu-id="e830c-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="e830c-109">本部分中的主题介绍如何在设计时使用的设置，运行时间。</span><span class="sxs-lookup"><span data-stu-id="e830c-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e830c-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="e830c-110">In This Section</span></span>  
 [<span data-ttu-id="e830c-111">如何：在设计时创建新设置</span><span class="sxs-lookup"><span data-stu-id="e830c-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="e830c-112">说明如何使用 Visual Studio 创建新的设置应用程序。</span><span class="sxs-lookup"><span data-stu-id="e830c-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="e830c-113">如何：在设计时更改现有设置的值</span><span class="sxs-lookup"><span data-stu-id="e830c-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="e830c-114">描述如何使用 Visual Studio 更改现有设置的值。</span><span class="sxs-lookup"><span data-stu-id="e830c-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="e830c-115">如何：在应用程序会话之间更改设置值</span><span class="sxs-lookup"><span data-stu-id="e830c-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="e830c-116">详细介绍如何更改应用程序会话之间编译的应用程序中的设置的值。</span><span class="sxs-lookup"><span data-stu-id="e830c-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="e830c-117">如何：在运行时使用 C# 读取设置</span><span class="sxs-lookup"><span data-stu-id="e830c-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="e830c-118">描述如何使用代码来读取使用 C# 的设置。</span><span class="sxs-lookup"><span data-stu-id="e830c-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="e830c-119">如何：在运行时使用 C# 编写用户设置</span><span class="sxs-lookup"><span data-stu-id="e830c-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="e830c-120">说明如何使用代码来编写和使用 C# 保存用户设置的值。</span><span class="sxs-lookup"><span data-stu-id="e830c-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="e830c-121">如何：使用 C# 向应用程序添加多组设置</span><span class="sxs-lookup"><span data-stu-id="e830c-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="e830c-122">详细介绍如何使用 C# 应用程序中添加多组设置。</span><span class="sxs-lookup"><span data-stu-id="e830c-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e830c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e830c-123">See Also</span></span>  
 [<span data-ttu-id="e830c-124">Windows 窗体的应用程序设置</span><span class="sxs-lookup"><span data-stu-id="e830c-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)
