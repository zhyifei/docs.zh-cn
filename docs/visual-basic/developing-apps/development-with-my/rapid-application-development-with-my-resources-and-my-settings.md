---
title: 使用 My.Resources 和 My.Settings 快速开发应用程序 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 808e02510d4f0a237ad4354b2edac8fa024b5f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>使用 My.Resources 和 My.Settings 快速开发应用程序 (Visual Basic)
`My.Resources`对象提供对应用程序的资源的访问，并允许你动态检索应用程序资源。  
  
## <a name="retrieving-resources"></a>检索资源  
 可以通过检索大量资源，例如音频文件、 图标、 图像和字符串`My.Resources`对象。 例如，你可以访问应用程序的区域性特定资源文件。 下面的示例设置窗体的图标名为的图标`Form1Icon`存储在应用程序的资源文件。  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources`对象公开仅全局资源。 它不提供对与窗体关联的资源文件的访问。 必须从窗体来访问窗体资源。  
  
 同样，`My.Settings`对象提供对应用程序的设置访问权限和可以动态存储和检索属性设置以及你的应用程序的其他信息。 有关详细信息，请参阅[My.Resources 对象](../../../visual-basic/language-reference/objects/my-resources-object.md)和[My.Settings 对象](../../../visual-basic/language-reference/objects/my-settings-object.md)。  
  
## <a name="see-also"></a>请参阅  
 [My.Resources 对象](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [My.Settings 对象](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [访问应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
