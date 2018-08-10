---
title: 如何：在自定义对象上实现验证逻辑
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: dbeddb5eb6996d5758717ddd2d4d5af0b6f57f3c
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "33555959"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>如何：在自定义对象上实现验证逻辑
此示例演示如何自定义对象上实现验证逻辑，然后绑定到它。  
  
## <a name="example"></a>示例  
 可以在业务层上提供验证逻辑，如果源对象实现<xref:System.ComponentModel.IDataErrorInfo>，如以下示例中，它定义`Person`对象，它实现<xref:System.ComponentModel.IDataErrorInfo>:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 以下示例中，在文本框中的 text 属性绑定到`Person.Age`属性，它变得可用于通过给定的资源声明绑定`x:Key` `data`。 <xref:System.Windows.Controls.DataErrorValidationRule>检查引起验证错误<xref:System.ComponentModel.IDataErrorInfo>实现。  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 或者，而不是使用<xref:System.Windows.Controls.DataErrorValidationRule>，可以设置<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>属性设置为`true`。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [实现绑定验证](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
