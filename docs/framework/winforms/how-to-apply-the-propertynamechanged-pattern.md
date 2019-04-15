---
title: 如何：应用 PropertyNameChanged 模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 36670eee6235277a7fe98770192df9ae05d3dd03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213020"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>如何：应用 PropertyNameChanged 模式
下面的代码示例演示如何将应用*PropertyName*Changed 模式的自定义控件。 实现自定义控件与 Windows 窗体数据绑定引擎配合使用时，将应用此模式。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>编译代码  
 若要编译前面的代码示例：  
  
-   将代码粘贴到空代码文件中。 必须使用包含在 Windows 窗体上的自定义控件`Main`方法。  
  
## <a name="see-also"></a>请参阅

- [如何：实现 INotifyPropertyChanged 接口](how-to-implement-the-inotifypropertychanged-interface.md)
- [Windows 窗体数据绑定中的更改通知](change-notification-in-windows-forms-data-binding.md)
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
