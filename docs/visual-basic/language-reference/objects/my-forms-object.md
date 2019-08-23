---
title: My Forms 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9fa5c77dd12c98100e3d17fc473a6802180d1e32
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965982"
---
# <a name="myforms-object"></a>My.Forms 对象
为访问在当前项目中声明的每个 Windows 窗体的实例提供属性。  
  
## <a name="remarks"></a>备注  
 `My.Forms`对象为当前项目中的每个窗体提供一个实例。 属性的名称与属性访问的窗体的名称相同。   
  
 您可以通过使用窗体的名称`My.Forms` , 而无需限定来访问由对象提供的窗体。 因为属性名称与窗体的类型名称相同, 所以这允许你像访问默认实例一样访问窗体。 例如，`My.Forms.Form1.Show` 与 `Form1.Show` 等效。  
  
 `My.Forms`对象只公开与当前项目关联的窗体。 它不提供对引用 Dll 中声明的窗体的访问。 若要访问 DLL 提供的窗体, 必须使用以*DllName*形式编写的格式的限定名称。*FormName*。  
  
 您可以使用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>属性来获取应用程序的所有打开窗体的集合。  
  
 对象及其属性仅适用于 Windows 应用程序。  
  
## <a name="properties"></a>属性  
 `My.Forms`对象的每个属性都提供对当前项目中窗体的实例的访问。 属性的名称与属性访问的窗体的名称相同, 属性类型与窗体的类型相同。  
  
> [!NOTE]
> 如果存在名称冲突, 则用于访问窗体的属性名称为*RootNamespace*_*命名空间*\_*FormName*。 例如, 假设有两个名`Form1.`为的窗体: 如果其中一个窗体`WindowsApplication1`位于根命名空间`Namespace1`和命名空间中, 则可以`My.Forms.WindowsApplication1_Namespace1_Form1`通过访问该窗体。  
  
 `My.Forms`对象提供对启动时创建的应用程序主窗体实例的访问权限。 对于所有其他窗体, `My.Forms`对象在被访问并存储时创建窗体的新实例。 后续尝试访问该属性将返回该窗体的实例。  
  
 您可以通过向窗体的属性`Nothing`分配来释放窗体。 属性 setter 调用<xref:System.Windows.Forms.Form.Close%2A>窗体的方法, 然后将分配`Nothing`给存储的值。 如果为属性分配除`Nothing`以外的任何值, 则 setter 会<xref:System.ArgumentException>引发异常。  
  
 您可以`My.Forms` `Is`使用or`IsNot`运算符测试对象的属性是否存储窗体的实例。 您可以使用这些运算符来检查属性的值是否为`Nothing`。  
  
> [!NOTE]
> 通常, `Is`或`IsNot`运算符必须读取属性的值才能执行比较。 但是, 如果属性当前存储`Nothing`, 则属性创建窗体的新实例, 然后返回该实例。 不过, Visual Basic 编译器会以不同的方式处理`My.Forms`对象的属性, 并`Is`允许`IsNot`或运算符检查属性的状态, 而无需更改其值。  
  
## <a name="example"></a>示例  
 此示例更改默认`SidebarMenu`窗体的标题。  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 要使此示例正常运行, 你的项目必须具有名`SidebarMenu`为的窗体。  
  
 此代码仅适用于 Windows 应用程序项目。  
  
## <a name="requirements"></a>要求  
  
### <a name="availability-by-project-type"></a>按项目类型的可用性  
  
|项目类型|可用|  
|---|---|  
|Windows 应用程序|**是**|  
|类库|No|  
|控制台应用程序|No|  
|Windows 控件库|No|  
|Web 控件库|No|  
|Windows 服务|No|  
|网站|No|  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [对象](../../../visual-basic/language-reference/objects/index.md)
- [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [访问应用程序窗体](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
