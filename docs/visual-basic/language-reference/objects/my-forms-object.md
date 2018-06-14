---
title: My.Forms 对象
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 4d6bb371b13dfb3fb735223b2a6a6a35e1416593
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603894"
---
# <a name="myforms-object"></a>My.Forms 对象
提供用于访问在当前项目中声明每个 Windows 窗体的实例的属性。  
  
## <a name="remarks"></a>备注  
 `My.Forms`对象提供当前项目中的每个窗体的实例。 属性访问的表单的名称相同的属性名称。   
  
 你可以访问提供的表单`My.Forms`对象使用窗体上，而无需限定的名称。 属性名称为与窗体的类型名称相同，因为这允许你访问窗体，就像它在默认实例。 例如，`My.Forms.Form1.Show` 与 `Form1.Show` 等效。  
  
 `My.Forms`对象公开仅与当前项目关联的窗体。 它不提供对在被引用的 Dll 中声明的表单的访问。 若要访问 DLL 提供窗体，你必须使用窗体中，编写为的限定的名称*dll 名称*。*窗体名称*。  
  
 你可以使用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>属性来获取应用程序的所有打开窗体的集合。  
  
 对象和其属性是仅适用于 Windows 应用程序。  
  
## <a name="properties"></a>属性  
 每个属性`My.Forms`对象提供对在当前项目的窗体的实例访问。 属性的名称属性访问时，表单的名称相同，因此该属性类型是窗体的类型相同。  
  
> [!NOTE]
>  如果没有名称冲突，属性名称来访问窗体是*RootNamespace*_*Namespace*\_*窗体名称*。 例如，考虑名为的两种形式`Form1.`这些窗体的其中一个是否根命名空间中`WindowsApplication1`和命名空间中`Namespace1`，你将访问该窗体通过`My.Forms.WindowsApplication1_Namespace1_Form1`。  
  
 `My.Forms`对象提供对在启动时创建的应用程序的主窗体实例访问。 对于所有其他窗体，`My.Forms`对象时它访问，并将其存储创建的窗体的新实例。 若要访问该属性的后续尝试返回该实例的窗体。  
  
 您可以通过分配释放窗体的`Nothing`到该窗体的属性。 属性 setter 调用<xref:System.Windows.Forms.Form.Close%2A>方法的窗体，然后将分配`Nothing`与存储的值。 如果不将任何值赋`Nothing`setter 的属性，将引发<xref:System.ArgumentException>异常。  
  
 你可以测试的属性是否`My.Forms`对象通过使用存储的窗体实例`Is`或`IsNot`运算符。 你可以使用这些运算符检查属性的值是否为`Nothing`。  
  
> [!NOTE]
>  通常情况下，`Is`或`IsNot`运算符具有要读取的属性进行比较的值。 但是，如果该属性当前存储`Nothing`，属性创建窗体的新实例，然后返回该实例。 但是，Visual Basic 编译器处理的属性`My.Forms`对象以不同的方式，并允许`Is`或`IsNot`运算符检查而不改变其值的属性的状态。  
  
## <a name="example"></a>示例  
 此示例将更改的默认标题`SidebarMenu`窗体。  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 对于此示例正常工作，你的项目必须具有名为窗体`SidebarMenu`。  
  
 此代码将仅适用于 Windows 应用程序项目。  
  
## <a name="requirements"></a>要求  
  
### <a name="availability-by-project-type"></a>项目类型的可用性  
  
|项目类型|可用|  
|---|---|  
|Windows 应用程序|**是**|  
|类库|否|  
|控制台应用程序|否|  
|Windows 控件库|否|  
|Web 控件库|否|  
|Windows 服务|否|  
|网站|否|  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [对象](../../../visual-basic/language-reference/objects/index.md)  
 [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [访问应用程序窗体](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
