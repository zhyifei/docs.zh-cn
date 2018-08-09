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
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="237c3-102">如何：在自定义对象上实现验证逻辑</span><span class="sxs-lookup"><span data-stu-id="237c3-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="237c3-103">此示例演示如何自定义对象上实现验证逻辑，然后绑定到它。</span><span class="sxs-lookup"><span data-stu-id="237c3-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="237c3-104">示例</span><span class="sxs-lookup"><span data-stu-id="237c3-104">Example</span></span>  
 <span data-ttu-id="237c3-105">可以在业务层上提供验证逻辑，如果源对象实现<xref:System.ComponentModel.IDataErrorInfo>，如以下示例中，它定义`Person`对象，它实现<xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="237c3-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="237c3-106">以下示例中，在文本框中的 text 属性绑定到`Person.Age`属性，它变得可用于通过给定的资源声明绑定`x:Key` `data`。</span><span class="sxs-lookup"><span data-stu-id="237c3-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="237c3-107"><xref:System.Windows.Controls.DataErrorValidationRule>检查引起验证错误<xref:System.ComponentModel.IDataErrorInfo>实现。</span><span class="sxs-lookup"><span data-stu-id="237c3-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="237c3-108">或者，而不是使用<xref:System.Windows.Controls.DataErrorValidationRule>，可以设置<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="237c3-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="237c3-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="237c3-109">See Also</span></span>  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [<span data-ttu-id="237c3-110">实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="237c3-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="237c3-111">帮助主题</span><span class="sxs-lookup"><span data-stu-id="237c3-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
