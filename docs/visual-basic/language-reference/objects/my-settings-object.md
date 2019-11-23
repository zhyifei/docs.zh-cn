---
title: My.Settings 对象
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350358"
---
# <a name="mysettings-object"></a>My.Settings 对象
Provides properties and methods for accessing the application's settings.  
  
## <a name="remarks"></a>备注  
 The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application. 有关详细信息，请参阅[管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)。  
  
## <a name="properties"></a>属性  
 `My.Settings` 对象的属性提供对应用程序设置的访问。 To add or remove settings, use the **Settings Designer**.  
  
 Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:  
  
- **Name** determines the name of the property.  
  
- **Type** determines the type of the property.  
  
- **Scope** indicates if the property is read-only. If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.  
  
- **Value** is the default value of the property.  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|---|---|  
|`Reload`|Reloads the user settings from the last saved values.|  
|`Save`|Saves the current user settings.|  
  
 The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.  
  
## <a name="tasks"></a>任务  
 The following table lists examples of tasks involving the `My.Settings` object.  
  
|功能|查看|  
|---|---|  
|Read an application setting|[如何：在 Visual Basic 中读取应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Change a user setting|[如何：在 Visual Basic 中更改用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Persist user settings|[如何：在 Visual Basic 中保存用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Create a property grid for user settings|[如何：在 Visual Basic 中创建用户设置的属性网格](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>示例  
 此示例显示 `Nickname` 设置的值。  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 若要使此示例正常工作，应用程序必须具有类型为 `String` 的 `Nickname` 设置。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Configuration.ApplicationSettingsBase>
- [如何：在 Visual Basic 中读取应用程序设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [如何：在 Visual Basic 中更改用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [如何：在 Visual Basic 中保存用户设置](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [如何：在 Visual Basic 中创建用户设置的属性网格](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [管理应用程序设置 (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
