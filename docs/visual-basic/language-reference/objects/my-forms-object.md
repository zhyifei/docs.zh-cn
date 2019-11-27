---
title: My.Forms 对象
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: db86704fdc8120ccac5f4489c80a515834ad888f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350364"
---
# <a name="myforms-object"></a>My.Forms 对象

为访问在当前项目中声明的每个 Windows 窗体的实例提供属性。

## <a name="remarks"></a>备注

`My.Forms` 对象提供当前项目中每个窗体的实例。 属性的名称与属性访问的窗体的名称相同。

您可以通过使用窗体的名称，而无需限定，来访问 `My.Forms` 对象提供的窗体。 因为属性名称与窗体的类型名称相同，所以这允许你像访问默认实例一样访问窗体。 例如，`My.Forms.Form1.Show` 与 `Form1.Show` 等效。

`My.Forms` 对象只公开与当前项目关联的窗体。 它不提供对引用 Dll 中声明的窗体的访问。 若要访问 DLL 提供的窗体，必须使用以*DllName*形式编写的格式的限定名称。*FormName*。

您可以使用 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> 属性获取应用程序的所有打开窗体的集合。

对象及其属性仅适用于 Windows 应用程序。

## <a name="properties"></a>属性

`My.Forms` 对象的每个属性都提供对当前项目中窗体的实例的访问。 属性的名称与属性访问的窗体的名称相同，属性类型与窗体的类型相同。

> [!NOTE]
> 如果存在名称冲突，则用于访问窗体的属性名称为*RootNamespace*_*Namespace*\_*FormName*。 例如，请考虑两个名为 `Form1.`的窗体。如果其中一个窗体位于根命名空间中 `WindowsApplication1` 在命名空间 `Namespace1`，则可以通过 `My.Forms.WindowsApplication1_Namespace1_Form1`访问该窗体。

`My.Forms` 对象提供对启动时创建的应用程序主窗体实例的访问权限。 对于所有其他窗体，`My.Forms` 对象在访问时将创建该窗体的新实例，并将其存储。 后续尝试访问该属性将返回该窗体的实例。

您可以通过将 `Nothing` 分配给该窗体的属性来释放窗体。 属性 setter 调用窗体的 <xref:System.Windows.Forms.Form.Close%2A> 方法，然后将 `Nothing` 赋给存储的值。 如果为属性分配除 `Nothing` 以外的任何值，则 setter 将引发 <xref:System.ArgumentException> 异常。

您可以使用 `Is` 或 `IsNot` 运算符测试 `My.Forms` 对象的属性是否存储窗体的实例。 您可以使用这些运算符来检查属性的值是否 `Nothing`。

> [!NOTE]
> 通常，`Is` 或 `IsNot` 运算符必须读取属性的值才能执行比较。 但是，如果属性当前存储 `Nothing`，则该属性将创建窗体的新实例，然后返回该实例。 不过，Visual Basic 编译器会以不同的方式对待 `My.Forms` 对象的属性，并允许 `Is` 或 `IsNot` 运算符检查属性的状态，而无需更改其值。

## <a name="example"></a>示例

此示例更改默认 `SidebarMenu` 窗体的标题。

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

要使此示例正常运行，你的项目必须具有名为 `SidebarMenu`的窗体。

此代码仅适用于 Windows 应用程序项目。

## <a name="requirements"></a>要求

### <a name="availability-by-project-type"></a>按项目类型的可用性

|项目类型|可用|
|---|---|
|Windows 应用程序|**是**|
|类库|是|
|控制台应用程序|是|
|Windows 控件库|是|
|Web 控件库|是|
|Windows 服务|是|
|网站|是|

## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [对象](../../../visual-basic/language-reference/objects/index.md)
- [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [访问应用程序窗体](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
