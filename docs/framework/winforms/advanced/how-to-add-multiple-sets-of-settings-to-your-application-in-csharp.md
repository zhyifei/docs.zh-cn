---
title: 如何：向应用程序添加多个设置组 (C#)
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 029dffc878c62613e291620a2bd86971f369d15a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520804"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>如何：向应用程序添加多个设置组 (C#) #
在某些情况下，你可能想要在应用程序具有多个集的设置。 例如，如果你正在开发的应用一组特定的设置需要经常更改，它可能是明智的做法是将它们分开所有导入到单个文件，以便该文件可以替换整个，使其他设置不受影响。 Visual Studio 允许你将多组设置添加到你的项目。 可以通过 Properties.Settings 对象访问设置的其他集。  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>将一组额外的设置添加到你的应用程序  
  
1.  从“项目”菜单中选择“添加新项”。 此时将打开“添加新项”对话框。  
  
2.  在**添加新项**对话框中，选择**设置文件**，键入，为文件的名称，然后单击**添加**将新的设置文件添加到你的解决方案。  
  
3.  在**解决方案资源管理器**，拖动到新的设置文件**属性**文件夹。 这允许你设置可在代码中使用新设置。  
  
4.  添加和使用此文件中的设置，就像任何其他设置文件。 你可以访问此组通过 Properties.Settings 对象的设置。  
  
## <a name="see-also"></a>请参阅  
 [使用应用程序设置和用户设置](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [应用程序设置概述](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
