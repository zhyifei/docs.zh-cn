---
title: My.Settings 对象
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 54176ae6706311b17227c7dc21a5060c9b369753
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603027"
---
# <a name="mysettings-object"></a>My.Settings 对象
提供属性和方法可以访问应用程序的设置。  
  
## <a name="remarks"></a>备注  
 `My.Settings`对象提供对应用程序的设置访问权限和可以动态存储和检索属性设置以及你的应用程序的其他信息。 有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。  
  
## <a name="properties"></a>属性  
 `My.Settings` 对象的属性提供对应用程序设置的访问。 若要添加或删除设置，使用**设置设计器**。  
  
 每个设置具有**名称**，**类型**，**作用域**，和**值**，并且这些设置确定如何用于访问每个设置的属性将出现在`My.Settings`对象：  
  
-   **名称**确定属性的名称。  
  
-   **类型**确定属性的类型。  
  
-   **作用域**指示属性是否是只读的。 如果值为**应用程序**，该属性是只读的; 如果值为**用户**，属性为读写。  
  
-   **值**是属性的默认值。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|---|---|  
|`Reload`|将重新加载上次保存的值中的用户设置。|  
|`Save`|将保存当前的用户设置。|  
  
 `My.Settings`对象还提供了高级的属性和方法，继承自<xref:System.Configuration.ApplicationSettingsBase>类。  
  
## <a name="tasks"></a>任务  
 下表列出了所涉及的任务的示例`My.Settings`对象。  
  
|到|查看|  
|---|---|  
|读取应用程序设置|[如何：在 Visual Basic 中读取应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|更改用户设置|[如何：在 Visual Basic 中更改用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|保存用户设置|[如何：在 Visual Basic 中保存用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|创建用户设置的属性网格|[如何：在 Visual Basic 中创建用户设置的属性网格](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>示例  
 此示例显示 `Nickname` 设置的值。  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 若要使此示例正常工作，应用程序必须具有类型为 `String` 的 `Nickname` 设置。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [如何：在 Visual Basic 中读取应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [如何：在 Visual Basic 中更改用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [如何：在 Visual Basic 中保存用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [如何：在 Visual Basic 中创建用户设置的属性网格](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
