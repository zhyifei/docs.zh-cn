---
title: 在 Windows 窗体控件中定义属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: dc47d7152419d55b3e52aec70257e2b39e9aaca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="defining-a-property-in-windows-forms-controls"></a>在 Windows 窗体控件中定义属性
有关属性的概述，请参阅[属性概述](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52)。 定义属性时需考虑以下重要注意事项：  
  
-   必须将特性应用于定义的属性。 特性指定设计器应如何显示属性。 有关详细信息，请参阅[组件的设计时特性](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)。  
  
-   如果更改该属性会影响控件的可视显示，调用<xref:System.Windows.Forms.Control.Invalidate%2A>方法 (您的控件继承自<xref:System.Windows.Forms.Control>) 从`set`访问器。 <xref:System.Windows.Forms.Control.Invalidate%2A> 反过来调用<xref:System.Windows.Forms.Control.OnPaint%2A>方法，重绘控件。 多次调用<xref:System.Windows.Forms.Control.Invalidate%2A>导致调用一次<xref:System.Windows.Forms.Control.OnPaint%2A>为提高效率。  
  
-   .NET Framework 类库为常见数据类型（如整数、小数、布尔值和其他数据类型）提供了类型转换器。 类型转换器的用途通常是提供字符串到数值的转换（从字符串数据转换为其他数据类型）。 常见数据类型与默认类型转换器相关联，默认类型转换器可将数值转换为字符串，并将字符串转换为相应数据类型。 如果定义了自定义（即非标准）数据类型的属性，则应用的特性必须将类型转换器指定为与该属性相关联。 还可使用特性将自定义 UI 类型编辑器与某个属性相关联。 UI 类型编辑器提供一个用于编辑属性或数据类型的用户界面。 UI 类型编辑器的一个例子是颜色选取器。 本主题末尾给出了特性的示例。  
  
    > [!NOTE]
    >  如果没有类型转换器或 UI 类型编辑器可供自定义属性使用，则可根据[扩展设计时支持](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)中所述来实现一个。  
  
 以下代码片段为自定义控件 `FlashTrackBar` 定义了一个名为 `EndColor` 的自定义属性。  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.   
   ' The Description attribute provides a description of  
   ' the property.   
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws    
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.   
   // The Description attribute provides a description of  
   // the property.   
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws   
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 以下代码片段将类型转换器和 UI 类型编辑器与属性 `Value` 相关联。 在这种情况下`Value`是一个整数，具有默认的类型转换器，但<xref:System.ComponentModel.TypeConverterAttribute>属性适用的自定义类型转换器 (`FlashTrackBarValueConverter`)，它使设计器，以显示为百分比。 UI 类型编辑器 `FlashTrackBarValueEditor` 允许以可视化方式显示百分比。 此示例还显示的类型转换器或编辑器指定<xref:System.ComponentModel.TypeConverterAttribute>或<xref:System.ComponentModel.EditorAttribute>特性将重写默认的转换器。  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),   
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件中的属性](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [使用 ShouldSerialize 和 Reset 方法定义默认值](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 [属性更改事件](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 [Windows 窗体控件中的特性](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)
