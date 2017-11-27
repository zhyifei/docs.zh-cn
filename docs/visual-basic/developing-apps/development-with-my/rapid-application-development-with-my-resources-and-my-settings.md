---
title: "使用 My.Resources 和 My.Settings 快速开发应用程序 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1657febf935560ff4c8dd2f54b10fdcb2254891f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>使用 My.Resources 和 My.Settings 快速开发应用程序 (Visual Basic)
`My.Resources`对象提供对应用程序的资源的访问，并允许你动态检索应用程序资源。  
  
## <a name="retrieving-resources"></a>检索资源  
 可以通过检索大量资源，例如音频文件、 图标、 图像和字符串`My.Resources`对象。 例如，你可以访问应用程序的区域性特定资源文件。 下面的示例设置窗体的图标名为的图标`Form1Icon`存储在应用程序的资源文件。  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources`对象公开仅全局资源。 它不提供对与窗体关联的资源文件的访问。 必须从窗体来访问窗体资源。 有关详细信息，请参阅[演练：本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)。  
  
 同样，`My.Settings`对象提供对应用程序的设置访问权限和可以动态存储和检索属性设置以及你的应用程序的其他信息。 有关详细信息，请参阅[My.Resources 对象](../../../visual-basic/language-reference/objects/my-resources-object.md)和[My.Settings 对象](../../../visual-basic/language-reference/objects/my-settings-object.md)。  
  
## <a name="see-also"></a>另请参阅  
 [My.Resources 对象](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [My.Settings 对象](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [访问应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
