---
title: 演练：使用 XAML 创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a0792beca358de52a24bd9bb0dd48a20c175f8ff
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920187"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>演练：使用 XAML 创建按钮

本演练的目的是了解如何创建在 Windows Presentation Foundation （WPF）应用程序中使用的动画按钮。 本演练使用样式和模板来创建自定义的按钮资源，以允许在按钮声明中重复使用代码和按钮逻辑分离。 本演练完全以 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]编写。

> [!IMPORTANT]
> 本演练将指导你完成创建应用程序的步骤，方法是在 Visual Studio 中键入或复制并粘贴 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。 如果希望了解如何使用设计器创建相同的应用程序，请参阅[使用 Microsoft Expression Blend 创建按钮](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)。

下图显示了 "已完成" 按钮。

![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>创建基本按钮

首先创建一个新项目，并向该窗口添加几个按钮。

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>创建新的 WPF 项目并向窗口中添加按钮

1. 启动 Visual Studio。

2. **创建新的 WPF 项目：** 在 "**文件**" 菜单上，指向 "**新建**"，然后单击 "**项目**"。 找到**Windows 应用程序（WPF）** 模板，并将项目命名为 "AnimatedButton"。 这将创建应用程序的主干。

3. **添加基本的默认按钮：** 此演练所需的所有文件都由模板提供。 在解决方案资源管理器中双击 Window1.xaml 文件，将其打开。 默认情况下，Window1.xaml 中有一个 <xref:System.Windows.Controls.Grid> 元素。 通过键入或复制以下突出显示的代码并将其粘贴到 Window1.xaml，删除 <xref:System.Windows.Controls.Grid> 元素并向 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 页添加几个按钮：

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     按 F5 运行该应用程序;应会看到如下图所示的一组按钮。

     ![三个基本按钮](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     现在，您已创建了基本按钮，接下来在 Window1.xaml 文件中完成工作。 本演练的其余部分侧重于 app.xaml 文件，为按钮定义样式和模板。

## <a name="set-basic-properties"></a>设置基本属性

接下来，让我们在这些按钮上设置一些属性，以控制按钮的外观和布局。 您将使用资源来定义整个应用程序的按钮属性，而不是单独设置按钮的属性。 应用程序资源在概念上类似于网页的外部级联样式表（CSS）;但是，资源比级联样式表（CSS）要强大得多，如本演练结束时所见。 若要了解有关资源的详细信息，请参阅[XAML 资源](../advanced/xaml-resources.md)。

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>使用样式设置按钮的基本属性

1. **定义应用程序 .resources 块：** 打开 app.xaml 并添加以下突出显示的标记（如果尚未存在）：

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

     资源范围由定义资源的位置确定。 在 app.xaml 文件的 `Application.Resources` 中定义资源后，可在应用程序中的任何位置使用资源。 若要了解有关定义资源范围的详细信息，请参阅[XAML 资源](../advanced/xaml-resources.md)。

2. **创建样式，并使用它定义基本属性值：** 将以下标记添加到 `Application.Resources` 块。 此标记将创建一个应用于应用程序中所有按钮的 <xref:System.Windows.Style>，并将这些按钮的 <xref:System.Windows.FrameworkElement.Width%2A> 设置为90，将 <xref:System.Windows.FrameworkElement.Margin%2A> 设置为10：

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <xref:System.Windows.Style.TargetType%2A> 属性指定样式应用于 <xref:System.Windows.Controls.Button>类型的所有对象。 每个 <xref:System.Windows.Setter> 为 <xref:System.Windows.Style>设置不同的属性值。 因此，应用程序中的每个按钮的宽度均为90，边距为10。  如果按 F5 运行该应用程序，将看到以下窗口。

     ![宽度为90，边距为10的按钮](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     您还可以对样式进行更多的操作，其中包括多种方法来微调目标对象、指定复杂的属性值，甚至使用样式作为其他样式的输入。 有关详细信息，请参阅[样式设置和模板化](styling-and-templating.md)。

3. **将样式属性值设置为资源：** 通过资源，可以使用一种简单的方法来重复使用通常定义的对象和值。 使用资源来定义复杂值非常有用，使代码更具模块化。 将以下突出显示的标记添加到 app.config。

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

     直接在 `Application.Resources` 块下创建名为 "GrayBlueGradientBrush" 的资源。 此资源定义水平渐变。 此资源可用作应用程序中任何位置的属性值，包括 <xref:System.Windows.Controls.Control.Background%2A> 属性的按钮样式 setter 内。 现在，所有按钮都具有此渐变的 <xref:System.Windows.Controls.Control.Background%2A> 属性值。

     按 F5 运行该应用程序。 其外观应如下所示。

     ![带有渐变背景的按钮](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>创建定义按钮外观的模板

在本部分中，将创建一个自定义按钮外观（表示）的模板。 按钮表示由多个对象组成，其中包括矩形和其他组件，用于为按钮指定独特的外观。

到目前为止，控件在应用程序中的外观控件限制为更改按钮的属性。 如果要对按钮的外观进行更多的根式更改，会怎么样？ 模板可以强大地控制对象的表示形式。 由于可以在样式内使用模板，因此可以将模板应用于样式应用到的所有对象（在本演练中为按钮）。

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>使用模板定义按钮的外观

1. **设置模板：** 由于 <xref:System.Windows.Controls.Button> 的控件具有 <xref:System.Windows.Controls.Control.Template%2A> 属性，因此可以像定义使用 <xref:System.Windows.Setter>在 <xref:System.Windows.Style> 中设置的其他属性值一样定义模板属性值。 将以下突出显示的标记添加到按钮样式。

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

2. **更改按钮演示：** 此时，需要定义模板。 添加以下突出显示的标记。 此标记指定两个带圆角的 <xref:System.Windows.Shapes.Rectangle> 元素，后跟一个 <xref:System.Windows.Controls.DockPanel>。 <xref:System.Windows.Controls.DockPanel> 用于承载按钮的 <xref:System.Windows.Controls.ContentPresenter>。 <xref:System.Windows.Controls.ContentPresenter> 显示按钮的内容。 在本演练中，内容是文本（"Button 1"、"Button 2"、"Button 3"）。 所有模板组件（矩形和 <xref:System.Windows.Controls.DockPanel>）都在 <xref:System.Windows.Controls.Grid>内进行布局。

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

     ![具有3个按钮的窗口](./media/custom-button-animatedbutton-4.gif)

3. **将 Glasseffect 添加到模板：** 接下来，你将添加玻璃。 首先，创建一些创建玻璃渐变效果的资源。 将这些渐变资源添加到 `Application.Resources` 块中的任何位置：

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     这些资源用作在按钮模板的 <xref:System.Windows.Controls.Grid> 中插入的矩形的 <xref:System.Windows.Shapes.Shape.Fill%2A>。 将以下突出显示的标记添加到模板。

    ```xaml
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
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
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
    </ControlTemplate>
    </Setter.Value>
    ```

     请注意，`x:Name` 属性为 "glassCube" 的矩形的 <xref:System.Windows.UIElement.Opacity%2A> 为0，因此，在运行该示例时，看不到顶部显示的玻璃矩形。 这是因为，稍后我们会将触发器添加到模板中，以便用户与按钮交互时。 不过，现在可以通过将 <xref:System.Windows.UIElement.Opacity%2A> 值更改为1并运行应用程序来查看按钮的外观。 请参见下图。 继续下一步之前，请将 <xref:System.Windows.UIElement.Opacity%2A> 更改回0。

     ![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>创建按钮交互性

在本部分中，你将创建属性触发器和事件触发器，以更改属性值，并运行动画来响应用户操作，例如，将鼠标指针移到按钮上并单击。

添加交互（鼠标悬停、鼠标离开、单击等）的一种简单方法是在模板或样式中定义触发器。 若要创建 <xref:System.Windows.Trigger>，请定义属性 "条件"，如：按钮 <xref:System.Windows.UIElement.IsMouseOver%2A> 属性值等于 `true`。 然后，定义在触发器条件为 true 时执行的 setter （操作）。

### <a name="to-create-button-interactivity"></a>若要创建按钮交互性

1. **添加模板触发器：** 将突出显示的标记添加到模板。

    ```xaml
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

2. **添加属性触发器：** 将突出显示的标记添加到 `ControlTemplate.Triggers` 块：

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     按 F5 运行应用程序，并在按钮上运行鼠标指针时查看效果。

3. **添加焦点触发器：** 接下来，我们将添加一些类似的 setter 来处理按钮有焦点的情况（例如，用户单击后）。

    ```xaml
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

     按 F5 运行应用程序，并单击其中一个按钮。 请注意，单击按钮后，按钮会保持突出显示，因为它仍有焦点。 如果单击另一个按钮，新按钮会获得焦点，而最后一个按钮丢失。

4. 为 <xref:System.Windows.UIElement.MouseEnter>**和**<xref:System.Windows.UIElement.MouseLeave>**添加动画** **：** 接下来，我们向触发器添加一些动画。 将以下标记添加到 `ControlTemplate.Triggers` 块内部的任意位置。

    ```xaml
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

     当鼠标指针移到按钮上并在指针离开时返回到正常大小时，玻璃矩形会收缩。

     当指针悬停在按钮上方时（引发<xref:System.Windows.UIElement.MouseEnter> 事件），会触发两个动画。 这些动画沿 X 和 Y 轴收缩玻璃矩形。 请注意 <xref:System.Windows.Media.Animation.DoubleAnimation> 元素上的属性，<xref:System.Windows.Media.Animation.Timeline.Duration%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>。 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 指定动画每半秒发生一次，<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 指定玻璃缩小10%。

     第二个事件触发器（<xref:System.Windows.UIElement.MouseLeave>）只是停止第一个触发器。 停止 <xref:System.Windows.Media.Animation.Storyboard>时，所有动画属性都将恢复为其默认值。 因此，当用户将指针移到按钮上时，按钮返回到鼠标指针移到按钮上之前的状态。 有关动画的详细信息，请参阅[动画概述](../graphics-multimedia/animation-overview.md)。

5. 在**单击按钮时添加动画：** 最后一步是在用户单击按钮时添加触发器。 将以下标记添加到 `ControlTemplate.Triggers` 块内部的任意位置：

    ```xaml
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

     按 F5 运行应用程序，然后单击其中一个按钮。 单击按钮时，玻璃矩形会旋转。

## <a name="summary"></a>总结
 在本演练中，您执行了以下练习：

- 目标为对象类型的 <xref:System.Windows.Style> （<xref:System.Windows.Controls.Button>）。

- 使用 <xref:System.Windows.Style>的整个应用程序中的按钮的受控基本属性。

- 创建了一些资源，如渐变要用于 <xref:System.Windows.Style> 资源库的属性值。

- 通过将模板应用于按钮，自定义了整个应用程序中的按钮的外观。

- 用于响应用户操作（例如 <xref:System.Windows.UIElement.MouseEnter>、<xref:System.Windows.UIElement.MouseLeave>和 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>）的按钮的自定义行为，这些操作包含了动画效果。

## <a name="see-also"></a>请参阅

- [使用 Microsoft Expression Blend 创建按钮](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [样式设置和模板化](styling-and-templating.md)
- [动画概述](../graphics-multimedia/animation-overview.md)
- [使用纯色和渐变进行绘制概述](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [位图效果概述](../graphics-multimedia/bitmap-effects-overview.md)
