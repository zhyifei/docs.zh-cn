---
title: 演练：使用 XAML 创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646469"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>演练：使用 XAML 创建按钮

本演练的目的是了解如何创建用于 Windows 演示文稿基础 （WPF） 应用程序的动画按钮。 本演练使用样式和模板创建自定义按钮资源，允许重用代码并将按钮逻辑与按钮声明分离。 本演练完全写在 中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。

> [!IMPORTANT]
> 本演练将指导您完成通过键入或复制并粘贴[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]到 Visual Studio 来创建应用程序的步骤。 如果您希望了解如何使用设计器创建相同的应用程序，请参阅[使用 Microsoft 表达式混合创建按钮](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)。

下图显示了已完成的按钮。

![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>创建基本按钮

让我们从创建新项目并向窗口添加几个按钮开始。

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>创建新的 WPF 项目并将按钮添加到窗口

1. 启动 Visual Studio。

2. **创建新的 WPF 项目：** 在 **"文件"** 菜单上，指向 **"新建**"，然后单击"**项目**"。 查找**Windows 应用程序 （WPF）** 模板并将项目命名为"动画按钮"。 这将为应用程序创建骨架。

3. **添加基本默认按钮：** 本演练所需的所有文件都由模板提供。 通过在解决方案资源管理器中双击 Window1.xaml 文件来打开该文件。 默认情况下，Window1.xaml 中存在一个<xref:System.Windows.Controls.Grid>元素。 通过键入<xref:System.Windows.Controls.Grid>或复制并将以下突出显示的代码粘贴到[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Window1.xaml，删除元素并将几个按钮添加到页面：

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

     按 F5 运行应用程序;您应该会看到一组按钮，如下所示。

     ![三个基本按钮](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     现在，您已经创建了基本按钮，您已完成在 Window1.xaml 文件中的工作。 演练的其余部分将侧重于 app.xaml 文件，定义样式和按钮的模板。

## <a name="set-basic-properties"></a>设置基本属性

接下来，让我们在这些按钮上设置一些属性，以控制按钮的外观和布局。 您将使用资源为整个应用程序定义按钮属性，而不是单独设置按钮上的属性。 应用程序资源在概念上类似于网页的外部级联样式表 （CSS）;但是，资源比级联样式表 （CSS） 更强大，正如在本演练结束时看到的。 要了解有关资源的更多信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>使用样式在按钮上设置基本属性

1. **定义应用程序.资源块：** 打开 app.xaml 并添加以下突出显示的标记（如果尚未出现）：

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

     资源范围由定义资源的位置确定。 在 app.xaml`Application.Resources`文件中定义资源，可以从应用程序中的任何位置使用资源。 要了解有关定义资源范围的更多信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。

2. **创建样式并使用它定义基本属性值：** 将以下标记添加到块中`Application.Resources`。 此标记创建<xref:System.Windows.Style>应用于应用程序中的所有按钮，将按钮设置为 90，将<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.FrameworkElement.Margin%2A>设置为 10：

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     属性<xref:System.Windows.Style.TargetType%2A>指定样式应用于 类型<xref:System.Windows.Controls.Button>的所有对象。 每个<xref:System.Windows.Setter>设置 不同的属性值。 <xref:System.Windows.Style> 因此，此时应用程序中的每个按钮的宽度为 90，边距为 10。  如果按 F5 运行应用程序，您将看到以下窗口。

     ![宽度为 90、边距为 10 的按钮](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     可以使用样式执行更多操作，包括调整目标对象、指定复杂属性值，甚至使用样式作为其他样式的输入的各种方法。 有关详细信息，请参阅[样式和模板](../../../desktop-wpf/fundamentals/styles-templates-overview.md)化。

3. **将样式属性值设置为资源：** 资源支持一种简单方法来重用通常定义的对象和值。 使用资源定义复杂值以使代码更加模块化尤其有用。 将以下突出显示的标记添加到 app.xaml。

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

     直接在`Application.Resources`块下，您创建了一个名为"灰蓝渐变画笔"的资源。 此资源定义水平渐变。 此资源可以从应用程序的任何位置用作属性值，包括在<xref:System.Windows.Controls.Control.Background%2A>属性的按钮样式设置器内。 现在，所有按钮都有此渐变<xref:System.Windows.Controls.Control.Background%2A>的属性值。

     按 F5 运行应用程序。 它应该如下所示。

     ![具有渐变背景的按钮](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>创建定义按钮外观的模板

在本节中，您将创建一个模板，用于自定义按钮的外观（表示）。 按钮表示由多个对象组成，包括矩形和其他组件，使按钮的外观独一无二。

到目前为止，对按钮在应用程序中的外观的控制仅限于更改按钮的属性。 如果你想对按钮的外观进行更彻底的更改，该怎么办？ 模板能够对对象的表示进行强大的控制。 由于模板可以在样式中使用，因此可以将模板应用于样式应用于的所有对象（在本演练中，按钮）。

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>使用模板定义按钮的外观

1. **设置模板：** 由于控件（<xref:System.Windows.Controls.Button>如具有<xref:System.Windows.Controls.Control.Template%2A>属性）可以定义模板属性值，就像我们<xref:System.Windows.Style>使用 中设置的其他属性值一<xref:System.Windows.Setter>样。 将以下突出显示的标记添加到按钮样式中。

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

2. **更改按钮演示文稿：** 此时，您需要定义模板。 添加以下突出显示的标记。 此标记指定两<xref:System.Windows.Shapes.Rectangle>个圆边元素，后跟 。 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.DockPanel>用于承载<xref:System.Windows.Controls.ContentPresenter>按钮的 。 显示<xref:System.Windows.Controls.ContentPresenter>按钮的内容。 在本演练中，内容是文本（"按钮 1"，"按钮 2"，"按钮 3"）。 所有模板组件（矩形和<xref:System.Windows.Controls.DockPanel>） 都位于 的<xref:System.Windows.Controls.Grid>内部。

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

     按 F5 运行应用程序。 它应该如下所示。

     ![带 3 个按钮的窗口](./media/custom-button-animatedbutton-4.gif)

3. **向模板添加玻璃效果：** 接下来，您将添加玻璃。 首先，创建一些创建玻璃渐变效果的资源。 在`Application.Resources`块内的任意位置添加这些渐变资源：

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

     这些资源用作<xref:System.Windows.Shapes.Shape.Fill%2A>我们插入到按钮模板<xref:System.Windows.Controls.Grid>中的矩形。 向模板添加以下突出显示的标记。

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

     请注意，<xref:System.Windows.UIElement.Opacity%2A>具有"glassCube"`x:Name`属性的矩形为 0，因此当您运行示例时，您看不到覆盖在顶部的玻璃矩形。 这是因为我们稍后将向模板添加触发器，用于用户与按钮交互时。 但是，通过将<xref:System.Windows.UIElement.Opacity%2A>值更改为 1 并运行应用程序，您可以看到按钮现在的外观。 请参阅下图。 在继续下一步之前，将<xref:System.Windows.UIElement.Opacity%2A>返回更改为 0。

     ![使用 XAML 创建的自定义按钮](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>创建按钮交互性

在本节中，您将创建属性触发器和事件触发器以更改属性值并运行动画以响应用户操作，例如将鼠标指针移到按钮上并单击。

添加交互性（鼠标悬停、鼠标离开、单击等）的一种简单方法是在模板或样式中定义触发器。 要创建<xref:System.Windows.Trigger>，定义属性"条件"，例如：按钮<xref:System.Windows.UIElement.IsMouseOver%2A>属性值等于`true`。 然后定义在触发条件为 true 时发生的设置器（操作）。

### <a name="to-create-button-interactivity"></a>创建按钮交互性

1. **添加模板触发器：** 将突出显示的标记添加到模板中。

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

2. **添加属性触发器：** 将突出显示的标记添加到`ControlTemplate.Triggers`块：

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     按 F5 以运行应用程序，并在在按钮上运行鼠标指针时看到效果。

3. **添加焦点触发器：** 接下来，我们将添加一些类似的设置器来处理按钮具有焦点时（例如，在用户单击按钮后）的情况。

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

     按 F5 运行应用程序，然后单击其中一个按钮。 请注意，单击该按钮后，该按钮将保持突出显示，因为它仍有焦点。 如果单击另一个按钮，则新按钮在上次按钮丢失时获得焦点。

4. **为**<xref:System.Windows.UIElement.MouseEnter>**和**<xref:System.Windows.UIElement.MouseLeave>添加动画 **：** 接下来，我们将一些动画添加到触发器中。   在`ControlTemplate.Triggers`块内的任意位置添加以下标记。

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

     当鼠标指针在按钮上移动时，玻璃矩形将缩小，当指针离开时返回正常大小。

     指针超过按钮时将触发两个动画（<xref:System.Windows.UIElement.MouseEnter>引发事件）。 这些动画沿 X 轴和 Y 轴收缩玻璃矩形。 请注意<xref:System.Windows.Media.Animation.DoubleAnimation>元素和<xref:System.Windows.Media.Animation.Timeline.Duration%2A>和 上的属性<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>。 指定<xref:System.Windows.Media.Animation.Timeline.Duration%2A>动画在半秒以上发生，并<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>指定玻璃收缩 10%。

     第二个事件触发器<xref:System.Windows.UIElement.MouseLeave>（ ） 只是停止第一个事件触发器。 停止 时，<xref:System.Windows.Media.Animation.Storyboard>所有动画属性将返回到其默认值。 因此，当用户将指针移出按钮时，该按钮将回到鼠标指针移到按钮之前的方式。 有关动画的详细信息，请参阅[动画概述](../graphics-multimedia/animation-overview.md)。

5. **添加单击按钮时的动画：** 最后一步是添加用户单击按钮时的触发器。 在`ControlTemplate.Triggers`块内的任意位置添加以下标记：

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
 在本演练中，您执行以下练习：

- 将<xref:System.Windows.Style>目标对象类型 （<xref:System.Windows.Controls.Button>。

- 使用 控制整个应用程序中按钮的基本属性<xref:System.Windows.Style>。

- 创建的资源（如渐变）用于<xref:System.Windows.Style>设置器的属性值。

- 通过将模板应用于按钮，自定义整个应用程序中的按钮外观。

- 按钮的自定义行为，以响应包含动画效果的用户操作（如<xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>、和<xref:System.Windows.Controls.Primitives.ButtonBase.Click>）。

## <a name="see-also"></a>另请参阅

- [使用 Microsoft Expression Blend 创建按钮](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [动画概述](../graphics-multimedia/animation-overview.md)
- [使用纯色和渐变进行绘制概述](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [位图效果概述](../graphics-multimedia/bitmap-effects-overview.md)
