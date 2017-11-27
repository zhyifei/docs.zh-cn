---
title: "如何：在自定义对象上实现验证逻辑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41a995223742e21f3bcc32d23c21882ac7eef465
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>如何：在自定义对象上实现验证逻辑
此示例演示如何在自定义对象上实现验证逻辑，然后绑定到它。  
  
## <a name="example"></a>示例  
 你可以在业务层提供验证逻辑，如果你的源对象实现<xref:System.ComponentModel.IDataErrorInfo>，下面的示例所示：  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 在下面的示例中，文本框的 text 属性将绑定到`Age`属性`Person`对象，该已可用于通过给定的资源声明的绑定对象`x:Key``data`。 <xref:System.Windows.Controls.DataErrorValidationRule>检查引发的验证错误<xref:System.ComponentModel.IDataErrorInfo>实现。  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 或者，而不是使用<xref:System.Windows.Controls.DataErrorValidationRule>，你可以设置<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>属性`true`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [实现绑定验证](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
