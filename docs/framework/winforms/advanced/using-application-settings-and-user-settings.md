---
title: 使用应用程序设置和用户设置
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: ea6994e653b3a06239634f5a0fddea84a07086e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777177"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="22a0c-102">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="22a0c-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="22a0c-103">从.NET Framework 2.0 开始，可以创建和访问应用程序执行会话之间保留的值。</span><span class="sxs-lookup"><span data-stu-id="22a0c-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="22a0c-104">这些值称为*设置*。</span><span class="sxs-lookup"><span data-stu-id="22a0c-104">These values are called *settings*.</span></span> <span data-ttu-id="22a0c-105">设置可以表示用户首选项，也需要使用应用程序的重要信息。</span><span class="sxs-lookup"><span data-stu-id="22a0c-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="22a0c-106">例如，可能会创建一系列存储的配色方案的应用程序的用户首选项的设置。</span><span class="sxs-lookup"><span data-stu-id="22a0c-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="22a0c-107">也可以存储指定应用程序使用的数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="22a0c-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="22a0c-108">设置，可以保持对外部代码，并创建存储单个用户的首选项的配置文件的应用程序至关重要的信息。</span><span class="sxs-lookup"><span data-stu-id="22a0c-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="22a0c-109">在本部分中的主题介绍如何在设计时使用的设置和运行时间。</span><span class="sxs-lookup"><span data-stu-id="22a0c-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22a0c-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="22a0c-110">In This Section</span></span>  
 [<span data-ttu-id="22a0c-111">如何：在设计时创建新的设置</span><span class="sxs-lookup"><span data-stu-id="22a0c-111">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="22a0c-112">介绍如何使用 Visual Studio 来创建新的应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="22a0c-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="22a0c-113">如何：在设计时的现有设置的值更改</span><span class="sxs-lookup"><span data-stu-id="22a0c-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="22a0c-114">介绍如何使用 Visual Studio 来更改现有设置的值。</span><span class="sxs-lookup"><span data-stu-id="22a0c-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="22a0c-115">如何：更改应用程序会话之间设置的值</span><span class="sxs-lookup"><span data-stu-id="22a0c-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="22a0c-116">详细介绍了如何更改应用程序会话之间的已编译应用程序中设置的值。</span><span class="sxs-lookup"><span data-stu-id="22a0c-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="22a0c-117">如何：在运行时读取设置C#</span><span class="sxs-lookup"><span data-stu-id="22a0c-117">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="22a0c-118">介绍如何使用代码来读取设置C#。</span><span class="sxs-lookup"><span data-stu-id="22a0c-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="22a0c-119">如何：在运行时编写用户设置C#</span><span class="sxs-lookup"><span data-stu-id="22a0c-119">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="22a0c-120">说明如何使用代码来编写和保存的用户设置的值C#。</span><span class="sxs-lookup"><span data-stu-id="22a0c-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="22a0c-121">如何：向应用程序中添加多组设置C#</span><span class="sxs-lookup"><span data-stu-id="22a0c-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="22a0c-122">详细介绍了如何使用应用程序中添加多组设置C#。</span><span class="sxs-lookup"><span data-stu-id="22a0c-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a0c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="22a0c-123">See also</span></span>

- [<span data-ttu-id="22a0c-124">Windows 窗体的应用程序设置</span><span class="sxs-lookup"><span data-stu-id="22a0c-124">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
