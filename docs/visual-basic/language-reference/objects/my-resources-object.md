---
title: "My.Resources 对象"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords: My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b2a2de7229f59e7deea29fe4186a5e466459d9fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="myresources-object"></a>My.Resources 对象
提供用于访问应用程序的资源的属性和类。  
  
## <a name="remarks"></a>备注  
 `My.Resources`对象提供了对应用程序的资源的访问，并允许动态检索应用程序的资源。 有关详细信息，请参阅[管理应用程序资源 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)。  
  
 `My.Resources`对象公开仅全局资源。 它不提供对与窗体关联的资源文件的访问。 必须从窗体来访问窗体资源。 有关详细信息，请参阅[演练：本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)。  
  
 你可以访问应用程序的区域性特定资源文件从`My.Resources`对象。 默认情况下，`My.Resources`对象查找中的区域性匹配的资源文件中的资源<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>属性。 但是，你可以重写此行为并指定特定区域性的资源使用。 有关详细信息，请参阅[桌面应用中的资源](../../../framework/resources/index.md)。  
  
## <a name="properties"></a>属性  
 属性`My.Resources`对象提供对应用程序的资源的只读访问。 若要添加或删除资源，使用**项目设计器**。 有关详细信息，请参阅[如何： 添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。 你可以访问通过添加资源**项目设计器**使用`My.Resources.``resourceName`。  
  
 你还可以添加或移除通过选择你的项目中的资源文件**解决方案资源管理器**并单击**添加新项**或**添加现有项**从**项目**菜单。 你可以访问通过使用这种方式添加的资源`My.Resources.``resourceFileName`.`resourceName`。  
  
 每个资源具有名称、 类别和值，并且这些资源设置确定要访问该资源的属性中的显示方式`My.Resources`对象。 在中添加的资源**项目设计器**:  
  
-   名称确定该属性的名称  
  
-   资源数据是，将该属性的值  
  
-   类别确定属性的类型：  
  
|类别|属性数据类型|  
|---|---|  
|**字符串**|[字符串](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**图像**|<xref:System.Drawing.Bitmap>|  
|**图标**|<xref:System.Drawing.Icon>|  
|**音频**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream>类派生自<xref:System.IO.Stream>类，以便它可使用的方法来以流，如<xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>方法。|  
|**文件**|-   [字符串](../../../visual-basic/language-reference/data-types/string-data-type.md)的文本文件。<br />-   <xref:System.Drawing.Bitmap>用于图像文件。<br />-   <xref:System.Drawing.Icon>图标文件。<br />-   <xref:System.IO.UnmanagedMemoryStream>声音文件。|  
|**其他**|由设计器中的信息确定**类型**列。|  
  
## <a name="classes"></a>类  
 `My.Resources`对象将作为具有共享属性的类公开每个资源文件。 类名称是资源文件的名称相同。 如前一部分中所述，作为在类中的属性被公开资源文件中的资源。  
  
## <a name="example"></a>示例  
 此示例将窗体的标题设置为字符串资源名称为`Form1Title`应用程序资源文件中。 对于该示例能工作，应用程序必须具有名为一个字符串`Form1Title`其资源文件中。 有关详细信息，请参阅[如何： 添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>示例  
 此示例将窗体的图标设置为名为图标`Form1Icon`存储在应用程序的资源文件。 对于该示例能工作，应用程序必须具有名为的图标`Form1Icon`其资源文件中。  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>示例  
 此示例中名为的图像资源设置窗体的背景图像`Form1Background`，这是在应用程序资源文件中。 对于此示例正常工作，应用程序必须具有名为图像资源`Form1Background`其资源文件中。  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>示例  
 此示例播放的声音，存储为音频资源名为`Form1Greeting`应用程序的资源文件中。 对于该示例能工作，应用程序必须具有名为音频资源`Form1Greeting`其资源文件中。 `My.Computer.Audio.Play`方法是仅适用于 Windows 窗体应用程序。  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>示例  
 此示例检索字符串资源的应用程序的法语区域性版本。 名为资源`Message`。 若要更改区域性，`My.Resources`对象使用，该示例使用<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>。  
  
 为此示例正常工作，应用程序必须具有名为字符串`Message`其资源中文件和应用程序应具有的资源文件，Resources.fr FR.resx 法语区域性版本。 有关详细信息，请参阅[如何： 添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。 如果应用程序不具有资源文件中，法语区域性版本`My.Resource`对象将从默认区域性资源文件中检索资源。  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [如何：添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)  
 [管理应用程序资源 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)  
 [桌面应用中的资源](../../../framework/resources/index.md)  
 [演练： 本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)
