---
title: "演练：使用 XAML 创建按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 543e6496c826c864dc77e50fd096fc4cb43f600e
ms.sourcegitcommit: 01ea3686e74ff05e4f6de3d8d46dc603d051ec00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2017
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>演练：使用 XAML 创建按钮
本演练的目的是了解如何创建用于动画的按钮[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]应用程序。 本演练使用样式和模板来创建自定义的按钮资源允许的代码重用，并从按钮声明的按钮逻辑分离。 本演练完全在编写[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。  
  
> [!IMPORTANT]
>  本演练将指导你逐步完成创建应用程序，通过键入或复制并粘贴[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]到 Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]。 如果你想要了解如何使用设计工具 (Microsoft Expression Blend) 来创建相同的应用程序，请参阅[创建通过使用 Microsoft Expression Blend 按钮](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)。  
  
 下图显示已完成的按钮。  
  
 ![使用 XAML 创建的自定义按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-basic-buttons"></a>创建基本按钮  
 让我们开始通过创建新的项目并将几个按钮添加到窗口。  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>创建新的 WPF 项目并将按钮添加到窗口  
  
1.  启动[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]。  
  
2.  **创建新的 WPF 项目：**上**文件**菜单上，指向**新建**，然后单击**项目**。 查找**Windows 应用程序 (WPF)**模板和名称的项目"AnimatedButton"。 这将创建应用程序的主干。  
  
3.  **添加基本的默认按钮：**对于本演练需要的所有文件都会都提供模板。 通过在解决方案资源管理器中单击双打开 Window1.xaml 文件。 默认情况下，没有<xref:System.Windows.Controls.Grid>Window1.xaml 中的元素。 删除<xref:System.Windows.Controls.Grid>元素和几个将按钮添加到[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]页上通过键入或者复制并粘贴到 Window1.xaml 以下突出显示的代码：  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     按 F5 运行该应用程序;你应看到一组类似于下图的按钮。  
  
     ![三个基本按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")  
  
     既然你已经创建基本的按钮，您已完成 Window1.xaml 文件中的工作。 本演练的其余部分重点介绍 app.xaml 文件中，定义样式和模板的按钮。  
  
## <a name="set-basic-properties"></a>设置基本属性  
 接下来，让我们在这些按钮来控制按钮外观和布局上设置某些属性。 而不是单独在按钮上设置属性，你将使用资源定义整个应用程序按钮属性。 应用程序资源是从概念上讲类似于外部[!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]Web 页; 但是，资源是比功能更强大[!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]，如你将看到按本演练结束。 若要了解有关资源的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>若要使用样式设置在按钮上的基本属性  
  
1.  **定义 Application.Resources 块：**打开 app.xaml 并添加以下突出显示的标记，如果它尚不存在：  
  
    ```xaml  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>  
    </Application>  
    ```  
  
     资源作用域取决于你在其中定义该资源。 定义中的资源`Application.Resources`在 app.xaml 文件允许使用从任何位置应用程序中的资源。 若要了解有关定义你的资源的作用域的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
2.  **创建一个样式，并定义基本属性值，其值：**添加到以下标记`Application.Resources`块。 此标记将创建<xref:System.Windows.Style>指示应用于应用程序设置中的所有按钮<xref:System.Windows.FrameworkElement.Width%2A>为 90 的按钮和<xref:System.Windows.FrameworkElement.Margin%2A>到 10:  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <xref:System.Windows.Style.TargetType%2A>属性指定该样式应用于类型的所有对象<xref:System.Windows.Controls.Button>。 每个<xref:System.Windows.Setter>设置不同的属性值为<xref:System.Windows.Style>。 因此，在此时应用程序中的每个按钮的宽度为 90，都边距为 10。  如果按 F5 运行该应用程序时，你将看到下面的窗口。  
  
     ![宽度为 90、 边距为 10 的按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")  
  
     没有你可以进行更多使用样式，包括各种方法来微调对象的目标，从而指定复杂的属性值，并甚至将用作输入其他样式的样式。 有关详细信息，请参阅[样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。  
  
3.  **样式属性值设置为资源：**资源，可以通过一种简单的方法，能够重复使用通常定义的对象和值。 它是特别有用，可以定义复杂值使用资源以使代码更加模块化。 将以下突出显示的标记添加到 app.xaml。  
  
    ```xaml  
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
    </Application.Resources>  
    ```  
  
     直接在`Application.Resources`块中，创建名为"GrayBlueGradientBrush"的资源。 该资源定义的水平的渐变。 可以从任何位置的属性值作为使用此资源应用程序，包括内部的按钮样式 setter 中<xref:System.Windows.Controls.Control.Background%2A>属性。 现在，所有按钮都有<xref:System.Windows.Controls.Control.Background%2A>此渐变的属性值。  
  
     按 F5 运行该应用程序。 其外观应如下所示。  
  
     ![具有渐变背景的按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a>创建定义按钮的外观的模板。  
 在本部分中，你将创建自定义按钮的外观 (presentation) 的模板。 按钮演示文稿组成包括矩形和其他组件的多个对象以使具有唯一外观的按钮。  
  
 到目前为止，应用程序中的按钮外观的控件已限制为更改该按钮的属性。 如果你想要按钮的外观做出更根本的更改？ 模板启用功能强大控制表示法的对象。 因为样式中，可以使用模板，你可以将模板应用于 （在本演练中，按钮），该样式应用到的所有对象。  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>若要使用模板来定义按钮的外观  
  
1.  **设置模板：**由于控件喜欢<xref:System.Windows.Controls.Button>具有<xref:System.Windows.Controls.Control.Template%2A>属性，可以定义模板属性值，就像我们已经设置了中的其他属性值一样<xref:System.Windows.Style>使用<xref:System.Windows.Setter>。 将以下突出显示的标记添加到按钮样式。  
  
    ```xaml
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>  
      </Style>  
    </Application.Resources>  
    ```  
  
2.  **Alter 按钮演示文稿：**此时，你需要定义模板。 添加以下突出显示的标记。 此标记指定的两个<xref:System.Windows.Shapes.Rectangle>具有圆角的元素后跟<xref:System.Windows.Controls.DockPanel>。 <xref:System.Windows.Controls.DockPanel>使用到主机<xref:System.Windows.Controls.ContentPresenter>的按钮。 A<xref:System.Windows.Controls.ContentPresenter>显示按钮的内容。 在本演练中，内容是文本 （"按钮 1"、"按钮 2"、"按钮 3"）。 所有模板组件 (矩形和<xref:System.Windows.Controls.DockPanel>) 的内部布局<xref:System.Windows.Controls.Grid>。  
  
    ```xaml  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     按 F5 运行该应用程序。 其外观应如下所示。  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")  
  
3.  **向模板添加玻璃：**接下来，您将添加玻璃。 首先创建某些资源的创建玻璃渐变效果。 添加这些渐变中的资源任意位置`Application.Resources`块：  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     这些资源将用作<xref:System.Windows.Shapes.Shape.Fill%2A>我们插入矩形<xref:System.Windows.Controls.Grid>的按钮模板。 向模板添加以下突出显示的标记。  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"  
    ClipToBounds="True">  
  
        <!-- Outer Rectangle with rounded corners. -->  
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
        <!-- Inner Rectangle with rounded corners. -->  
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"   
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />  
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     请注意，<xref:System.Windows.UIElement.Opacity%2A>的矩形`x:Name`"glassCube"属性为 0，当运行示例时，你看不到上面的玻璃矩形。 这是因为我们将更高版本将触发器添加到的模板使用按钮在用户交互时。 但是，你可以看到该按钮如下所示现在通过更改<xref:System.Windows.UIElement.Opacity%2A>到 1 和运行应用程序的值。 请参见下图。 在继续之前执行下一步，更改<xref:System.Windows.UIElement.Opacity%2A>回 0。  
  
     ![使用 XAML 创建的自定义按钮](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-button-interactivity"></a>创建按钮交互性  
 在本部分中，你将创建属性触发器和事件触发器以更改属性值并响应用户操作，例如将鼠标指针移到按钮上方和单击运行动画。  
  
 添加交互性 （鼠标悬停、 鼠标离开、 单击，依次类推） 的简单方法是定义模板或样式中的触发器。 若要创建<xref:System.Windows.Trigger>，如定义属性"条件": 按钮<xref:System.Windows.UIElement.IsMouseOver%2A>属性值等于`true`。 随后，你定义的触发器条件为 true 时要发生的 setter （操作）。  
  
#### <a name="to-create-button-interactivity"></a>若要创建按钮交互性  
  
1.  **添加模板触发器：**将突出显示的标记添加到你的模板。  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}"   
          Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"   
          />  
  
          <!-- Glass Rectangle -->  
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"  
            VerticalAlignment="Stretch"  
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"  
            Fill="{StaticResource MyGlassBrushResource}"  
            RenderTransformOrigin="0.5,0.5">  
            <Rectangle.Stroke>  
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">  
                <LinearGradientBrush.GradientStops>  
                  <GradientStop Offset="0.0" Color="LightBlue" />  
                  <GradientStop Offset="1.0" Color="Gray" />  
                </LinearGradientBrush.GradientStops>  
              </LinearGradientBrush>  
            </Rectangle.Stroke>  
  
            <!-- These transforms have no effect as they   
                 are declared here.   
                 The reason the transforms are included is to be targets   
                 for animation (see later). -->  
            <Rectangle.RenderTransform>  
              <TransformGroup>  
                <ScaleTransform />  
                <RotateTransform />  
              </TransformGroup>  
            </Rectangle.RenderTransform>  
  
              <!-- A BevelBitmapEffect is applied to give the button a   
                   "Beveled" look. -->  
            <Rectangle.BitmapEffect>  
              <BevelBitmapEffect />  
            </Rectangle.BitmapEffect>  
          </Rectangle>  
  
          <!-- Present Text of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
  
        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **添加属性触发器：**添加到突出显示的标记`ControlTemplate.Triggers`块：  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     按 F5 运行应用程序，然后在你运行鼠标指针在按钮上查看的效果。  
  
3.  **将焦点触发器添加：**接下来，我们将添加一些类似的 setter 以处理的情况，在按钮获得焦点 （例如，在用户单击它） 时。  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user          mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     按 F5 运行应用程序，然后单击一个按钮。 请注意后单击因为它仍然具有焦点的按钮始终保持突出显示。 如果单击另一个按钮时，新建按钮将获得焦点，而最后一个失去它。  
  
4.  **添加的动画效果**<xref:System.Windows.UIElement.MouseEnter> **和** <xref:System.Windows.UIElement.MouseLeave> **:**接下来我们将某些动画添加到触发器。 添加以下标记内部的任意位置`ControlTemplate.Triggers`块。  
  
    ```  
    <!-- Animations that start when mouse enters and leaves button. -->  
    <EventTrigger RoutedEvent="Mouse.MouseEnter">  
      <EventTrigger.Actions>  
        <BeginStoryboard Name="mouseEnterBeginStoryboard">  
          <Storyboard>  
          <!-- This animation makes the glass rectangle shrink in the X direction. -->  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"  
              By="-0.1" Duration="0:0:0.5" />  
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->  
            <DoubleAnimation  
            Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"   
              By="-0.1" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    <EventTrigger RoutedEvent="Mouse.MouseLeave">  
      <EventTrigger.Actions>  
        <!-- Stopping the storyboard sets all animated properties back to default. -->  
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     玻璃矩形收缩当鼠标指针移到按钮，并将返回到正常大小，当指针离开。  
  
     有两个指针移到该按钮时，触发的动画 (<xref:System.Windows.UIElement.MouseEnter>引发事件)。 这些动画收缩沿 X 和 Y 轴的玻璃矩形。 请注意，属性在<xref:System.Windows.Media.Animation.DoubleAnimation>元素-<xref:System.Windows.Media.Animation.Timeline.Duration%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>。 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>指定动画发生超过半秒，和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>指定玻璃收缩 10%。  
  
     第二个事件触发器 (<xref:System.Windows.UIElement.MouseLeave>) 就会停止运行的第一个。 当您停止<xref:System.Windows.Media.Animation.Storyboard>，所有动画的属性将返回到其默认值。 因此，当用户将指针离开按钮，该按钮将返回前鼠标指针移到按钮它所处的方式。 有关动画的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
5.  **添加动画时单击该按钮：**的最后一步是添加当用户单击按钮的触发器。 添加以下标记内部的任意位置`ControlTemplate.Triggers`块：  
  
    ```  
    <!-- Animation fires when button is clicked, causing glass to spin.  -->  
    <EventTrigger RoutedEvent="Button.Click">  
      <EventTrigger.Actions>  
        <BeginStoryboard>  
          <Storyboard>  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"   
              By="360" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     按 f5 键以运行该应用程序，并单击一个按钮。 当你单击按钮时，会旋转玻璃矩形。  
  
## <a name="summary"></a>摘要  
 在本演练中，您可以执行以下练习：  
  
-   目标<xref:System.Windows.Style>到对象类型 (<xref:System.Windows.Controls.Button>)。  
  
-   控制在整个应用程序中使用的按钮的基本属性<xref:System.Windows.Style>。  
  
-   创建资源，如渐变来对属性值的使用<xref:System.Windows.Style>setter。  
  
-   通过将模板应用于按钮自定义在整个应用程序中的按钮的外观。  
  
-   自定义以响应用户操作的按钮的行为 (如<xref:System.Windows.UIElement.MouseEnter>， <xref:System.Windows.UIElement.MouseLeave>，和<xref:System.Windows.Controls.Primitives.ButtonBase.Click>)，包含动画效果。  
  
## <a name="see-also"></a>另请参阅  
 [使用 Microsoft Expression Blend 创建按钮](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [位图效果概述](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
