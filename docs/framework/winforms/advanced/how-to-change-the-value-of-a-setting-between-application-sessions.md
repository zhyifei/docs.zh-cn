---
title: 如何：在应用程序会话间更改设置的值
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 95e613cb280813cd75d887d3cf147d7c897bc2e6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318880"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="5a70d-102">如何：在应用程序会话间更改设置的值</span><span class="sxs-lookup"><span data-stu-id="5a70d-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="5a70d-103">有时，你可能想要更改设置后编译和部署应用程序的应用程序会话之间的值。</span><span class="sxs-lookup"><span data-stu-id="5a70d-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="5a70d-104">例如，你可能想要更改连接字符串以指向正确的数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="5a70d-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="5a70d-105">由于编译和部署应用程序后，设计时工具不可用，则必须更改文件中手动设置值。</span><span class="sxs-lookup"><span data-stu-id="5a70d-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="5a70d-106">若要更改应用程序会话之间设置的值</span><span class="sxs-lookup"><span data-stu-id="5a70d-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1. <span data-ttu-id="5a70d-107">使用 Microsoft 记事本或一些其他文本或 XML 编辑器，打开你的应用程序与关联的.config 文件。</span><span class="sxs-lookup"><span data-stu-id="5a70d-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2. <span data-ttu-id="5a70d-108">找到你想要更改的设置的条目。</span><span class="sxs-lookup"><span data-stu-id="5a70d-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="5a70d-109">它应类似于下面显示的示例。</span><span class="sxs-lookup"><span data-stu-id="5a70d-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. <span data-ttu-id="5a70d-110">键入您的设置的新值并保存文件。</span><span class="sxs-lookup"><span data-stu-id="5a70d-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a70d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a70d-111">See also</span></span>

- [<span data-ttu-id="5a70d-112">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="5a70d-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="5a70d-113">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="5a70d-113">Application Settings Overview</span></span>](application-settings-overview.md)
