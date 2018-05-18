---
title: 如何：在 .NET Framework 流与 Windows 运行时流之间转换
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f67f88cd7f690e56664fa45878d1c9ac1f8a6b6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-between-net-framework-streams-and-windows-runtime-streams"></a>如何：在 .NET Framework 流与 Windows 运行时流之间转换
适用于 Windows 应用商店应用的 .NET Framework 是完整的 .NET Framework 的子集。 由于 Windows 应用商店应用的安全性和其他要求，你无法使用整套 .NET Framework API 来打开和读取文件。 有关详细信息，请参阅 [适用于 Windows 应用商店应用的 .NET 概述](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)。 但是，你可能需要将 .NET Framework API 用于其他流处理操作。 若要操作这些流，你可能会发现在 .NET Framework 流类型（如 <xref:System.IO.MemoryStream> 或 <xref:System.IO.FileStream>）和 Windows 运行时流（如 [IInputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.iinputstream.aspx)、 [IOutputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ioutputstream.aspx)或 [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx)）之间进行转换非常重要。  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` 类包含简化这些转换的方法。 但是，.NET Framework 中的流与 Windows 运行时中的流之间存在一些基本差异，这将影响使用这些方法所获得的结果。 后续各节描述了详细信息。  
  
<a name="BKMK_ConvertingfromaWindowsRuntimestreamtoaNETFrameworkstream"></a>   
## <a name="converting-from-a-windows-runtime-stream-to-a-net-framework-stream"></a>从 Windows 运行时流转换为 .NET Framework 流  
 你可以使用下列 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` 方法之一，从 Windows 运行时流转换为 .NET Framework 流：  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStream`  
 将 Windows 运行时中的随机访问流转换为适用于 Windows 应用商店应用的 .NET 子集中的托管流。  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite`
 将 Windows 运行时中的输出流转换为适用于 Windows 应用商店应用的 .NET 子集中的托管流。  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead`  
 将 Windows 运行时中的输入流转换为适用于 Windows 应用商店应用的 .NET 子集中的托管流。  
  
 Windows 运行时提供支持只读、只写或读写的流类型，并且在将 Windows 运行时流转换为 .NET Framework 流时，这些功能将保留。 此外，如果你在 Windows 运行时流与 .NET Framework 流之间转换，则将取回原始 Windows 运行时实例。 最佳做法是使用与要转换的 Windows 运行时流的功能匹配的转换方法。 但是，由于 [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx) 是可读写的（它同时实现了 [IOutputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ioutputstream.aspx) 和 [IInputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.iinputstream.aspx)），因此你可以使用任何转换方法，并且原始流的功能将保留。 例如，使用 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead` 转换 [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx) 不会将转换的 .NET Framework 流限制为只读；它也将是可写的。  
  
#### <a name="to-convert-from-a-windows-runtime-random-access-stream-to-a-net-framework-stream"></a>从 Windows 运行时随机访问流转换为 .NET Framework 流  
  
-   使用 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStream` 方法。  
  
     下面的代码示例演示如何提示用户选择文件，利用 Windows 运行时 API 将其打开，然后将其转换为可读取和输出到文本块中的 .NET Framework 流。 在此方案中，在输出结果之前，你通常使用 .NET Framework API 操作流。  
  
     若要运行此示例，你必须创建包含一个名为 `TextBlock1` 的文本块和一个名为  `Button1`的按钮的 Windows 应用商店 XAML 应用。 按钮单击事件必须与此示例中所示的 `button1_Click` 方法关联。  
  
     [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
     [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]  
    [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#1)]
    [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#1)]  
  
<a name="BKMK_ConvertingfromaNETFrameworkstreamtoaWindowsRuntimestream"></a>   
## <a name="converting-from-a-net-framework-stream-to-a-windows-runtime-stream"></a>从 .NET Framework 流转换为 Windows 运行时流  
 你可以使用下列 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` 方法之一，从 .NET Framework 流转换为 Windows 运行时流：  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsInputStream`  
 将适用于 Windows 应用商店应用的 .NET 子集中的托管流转换为 Windows 运行时中的输入流。  
  
<!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsOutputStream%2A>  --> `System.IO.WindowsRuntimeStreamExtensions.AsOutputStream`
 将适用于 Windows 应用商店应用的 .NET 子集中的托管流转换为 Windows 运行时中的输出流。  
  
 [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md)  
 将适用于 Windows 应用商店应用的 .NET 子集中的托管流转换为 Windows 运行时中可用于读取或写入的随机访问流。  
  
 在将 .NET Framework 流转换为 Windows 运行时流时，转换后的流的功能将取决于原始流。 例如，如果原始流支持读取和写入，并且你调用 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsInputStream` 来转换流，则返回的类型将为 `IRandomAccessStream`，它实现  `IInputStream` 和 `IOutputStream`并支持读取和写入  
  
 .NET Framework 流不支持克隆，即使转换后也是如此。 这意味着，如果你将 .NET Framework 流转换为 Windows 运行时流，并调用 [GetInputStreamAt](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.inmemoryrandomaccessstream.getinputstreamat.aspx) 或 [GetOutputStreamAt](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.getoutputstreamat.aspx)（这会直接调用 [CloneStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstreamoverstream.clonestream.aspx) 或 [CloneStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstreamoverstream.clonestream.aspx) ），则会引发异常。  
  
#### <a name="to-convert-from-a-net-framework-stream-to-a-windows-runtime-random-access-stream"></a>将 .NET Framework 流转换为 Windows 运行时随机访问流  
  
-   使用 [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md) 方法，如下面的示例所示。  
  
    > [!IMPORTANT]
    >  确保所使用的 .NET Framework 流支持查找或将其复制到支持查找的流。 可使用 <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType> 属性来确定这一点。  
  
     若要运行此示例，你必须创建一个面向 .NET Framework 4.5.1 的且包含一个名为 `TextBlock2` 的文本块和一个名为 `Button2`的按钮的 Windows 应用商店 XAML 应用。 按钮单击事件必须与此示例中所示的 `button2_Click` 方法关联。  
  
     [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
     [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]  
    [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#2)]
    [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [快速入门：对文件执行读取和写入操作 (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx)  
 [适用于 Microsoft Store 应用的 .NET 概述](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [适用于 Windows 应用商店应用的 .NET - 支持的 API](https://msdn.microsoft.com/library/windows/apps/br230232.aspx)
