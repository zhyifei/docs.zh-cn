---
title: "如何：在应用程序会话之间更改设置值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c00e61001d9c8877b1fcaa0e938c92249c7915e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="af48e-102">如何：在应用程序会话之间更改设置值</span><span class="sxs-lookup"><span data-stu-id="af48e-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="af48e-103">有时，你可能想要更改设置编译应用程序并将其部署之后的应用程序会话之间的值。</span><span class="sxs-lookup"><span data-stu-id="af48e-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="af48e-104">例如，你可能想要更改连接字符串以指向正确的数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="af48e-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="af48e-105">由于编译应用程序并将其部署之后，设计时工具不可用，则必须更改在该文件中手动设置值。</span><span class="sxs-lookup"><span data-stu-id="af48e-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="af48e-106">若要更改应用程序会话之间设置的值</span><span class="sxs-lookup"><span data-stu-id="af48e-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="af48e-107">使用 Microsoft 记事本或某些其他文本或 XML 编辑器，打开你的应用程序与关联的.config 文件。</span><span class="sxs-lookup"><span data-stu-id="af48e-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="af48e-108">找到你想要更改的设置的项。</span><span class="sxs-lookup"><span data-stu-id="af48e-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="af48e-109">其外观应类似于下面给出的示例。</span><span class="sxs-lookup"><span data-stu-id="af48e-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="af48e-110">键入你的设置的新值并保存文件。</span><span class="sxs-lookup"><span data-stu-id="af48e-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af48e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="af48e-111">See Also</span></span>  
 [<span data-ttu-id="af48e-112">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="af48e-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="af48e-113">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="af48e-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
