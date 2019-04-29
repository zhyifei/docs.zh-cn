---
title: 如何：在运行时编写用户设置 (C#)
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 264fa9706f9255d7324cad6d02c36cc424e28995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778828"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="b8e31-102">如何：在使用 C 运行时编写用户设置\#</span><span class="sxs-lookup"><span data-stu-id="b8e31-102">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="b8e31-103">应用程序范围的设置是只读的，只能在设计时更改，或通过在应用程序会话之间更改 .config 文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="b8e31-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="b8e31-104">但用户范围的设置可以在运行时写入，就像更改任何属性值一样。</span><span class="sxs-lookup"><span data-stu-id="b8e31-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="b8e31-105">新值在应用程序会话的持续时间内始终存在。</span><span class="sxs-lookup"><span data-stu-id="b8e31-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="b8e31-106">可以通过调用 Save 方法在应用程序会话之间保留对设置的更改。</span><span class="sxs-lookup"><span data-stu-id="b8e31-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="b8e31-107">如何：编写并使用 C 运行时保存用户设置\#</span><span class="sxs-lookup"><span data-stu-id="b8e31-107">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="b8e31-108">访问设置并向其分配新值，如本示例中所示：</span><span class="sxs-lookup"><span data-stu-id="b8e31-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="b8e31-109">如果想要到在应用程序会话之间保留对设置的更改，请调用 Save 方法，如本示例中所示：</span><span class="sxs-lookup"><span data-stu-id="b8e31-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="b8e31-110">用户设置保存在用户的本地应用程序数据文件夹（隐藏）中子文件夹下的文件内。</span><span class="sxs-lookup"><span data-stu-id="b8e31-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e31-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e31-111">See also</span></span>

- [<span data-ttu-id="b8e31-112">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="b8e31-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="b8e31-113">如何：在运行时读取设置C#</span><span class="sxs-lookup"><span data-stu-id="b8e31-113">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="b8e31-114">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="b8e31-114">Application Settings Overview</span></span>](application-settings-overview.md)
