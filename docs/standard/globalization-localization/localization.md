---
title: "本地化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a><span data-ttu-id="4cf7c-102">本地化</span><span class="sxs-lookup"><span data-stu-id="4cf7c-102">Localization</span></span>
<span data-ttu-id="4cf7c-103">本地化是将应用程序的资源翻译为该应用程序将支持每种区域性的本地化版本的过程。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="4cf7c-104">应继续完成后，仅本地化步[本地化分析检查](../../../docs/standard/globalization-localization/localizability-review.md)步骤以验证全球化应用程序是否准备好进行本地化。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="4cf7c-105">应用程序进行本地化了分为两个概念块、 包含所有用户界面元素的块和都包含可执行代码的块。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="4cf7c-106">用户界面块包含仅可本地化的用户界面元素，如字符串、 错误消息、 对话框、 菜单、 嵌入的对象，依次类推非特定区域性资源。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="4cf7c-107">代码块仅包含应用程序代码用于所有支持的区域性。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="4cf7c-108">公共语言运行时支持与其资源分隔应用程序的可执行代码的附属程序集资源模型。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="4cf7c-109">有关实现此模型的详细信息，请参阅[桌面应用中的资源](../../../docs/framework/resources/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="4cf7c-110">你的应用程序每个本地化版本，将添加新附属程序集包含本地化的用户界面块转换为适当的语言为目标区域性。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="4cf7c-111">所有区域性的代码块应保持不变。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="4cf7c-112">代码块的用户界面块的本地化版本的组合生成你的应用程序的本地化的版本。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="4cf7c-113">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]提供 Windows 窗体资源编辑器 (Winres.exe)，您可以快速为目标区域性本地化 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="4cf7c-114">有关使用此工具的信息，请参阅[Winres.exe （Windows 窗体资源编辑器）](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="4cf7c-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf7c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cf7c-115">See Also</span></span>  
 [<span data-ttu-id="4cf7c-116">全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="4cf7c-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="4cf7c-117">可本地化性审核</span><span class="sxs-lookup"><span data-stu-id="4cf7c-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="4cf7c-118">全球化</span><span class="sxs-lookup"><span data-stu-id="4cf7c-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="4cf7c-119">桌面应用中的资源</span><span class="sxs-lookup"><span data-stu-id="4cf7c-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
