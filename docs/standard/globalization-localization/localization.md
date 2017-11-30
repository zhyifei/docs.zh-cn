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
# <a name="localization"></a>本地化
本地化是将应用程序的资源翻译为该应用程序将支持每种区域性的本地化版本的过程。 应继续完成后，仅本地化步[本地化分析检查](../../../docs/standard/globalization-localization/localizability-review.md)步骤以验证全球化应用程序是否准备好进行本地化。  
  
 应用程序进行本地化了分为两个概念块、 包含所有用户界面元素的块和都包含可执行代码的块。 用户界面块包含仅可本地化的用户界面元素，如字符串、 错误消息、 对话框、 菜单、 嵌入的对象，依次类推非特定区域性资源。 代码块仅包含应用程序代码用于所有支持的区域性。 公共语言运行时支持与其资源分隔应用程序的可执行代码的附属程序集资源模型。 有关实现此模型的详细信息，请参阅[桌面应用中的资源](../../../docs/framework/resources/index.md)。  
  
 你的应用程序每个本地化版本，将添加新附属程序集包含本地化的用户界面块转换为适当的语言为目标区域性。 所有区域性的代码块应保持不变。 代码块的用户界面块的本地化版本的组合生成你的应用程序的本地化的版本。  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]提供 Windows 窗体资源编辑器 (Winres.exe)，您可以快速为目标区域性本地化 Windows 窗体。 有关使用此工具的信息，请参阅[Winres.exe （Windows 窗体资源编辑器）](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)。  
  
## <a name="see-also"></a>另请参阅  
 [全球化和本地化](../../../docs/standard/globalization-localization/index.md)  
 [可本地化性审核](../../../docs/standard/globalization-localization/localizability-review.md)  
 [全球化](../../../docs/standard/globalization-localization/globalization.md)  
 [桌面应用中的资源](../../../docs/framework/resources/index.md)
