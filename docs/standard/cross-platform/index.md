---
title: "使用 .NET Framework 针对多个平台开发"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9acceb04ea48ef7d9a99d8a82c63090ee344ea54
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="developing-for-multiple-platforms-with-the-net-framework"></a>使用 .NET Framework 针对多个平台开发
可以通过使用 .NET Framework 和 Visual Studio 开发 Microsoft 和非 Microsoft 平台上的应用。  
  
## <a name="options-for-cross-platform-development"></a>跨平台开发的选项  
 若要针对多个平台进行开发，你可以共享源代码或二进制文件，并可以在 .NET Framework 代码和 Windows 运行时 API 之间进行调用。  
  
|若希望...|使用...|  
|-----------------------|------------|  
|在 Windows Phone 8.1 和 Windows 8.1 应用之间共享源代码|**共享项目**（在 Visual Studio 2013 中，更新 2 的通用应用模板）。<br /><br /> -当前不支持 Visual Basic。<br />-你可以分隔平台特定的代码通过使用 #`if`语句。<br /><br /> 有关详细信息，请参见：<br /><br /> -   [生成应用程序通过使用 Visual Studio 来面向 Windows 和 Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) （MSDN 文章）<br />-   [使用 Visual Studio 来构建通用 XAML 应用](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx)（博客文章）<br />-   [使用 Visual Studio 构建 XAML 融合应用](http://channel9.msdn.com/Events/Build/2014/3-591)（视频）|  
|在面向不同平台的应用之间共享二进制文件|**可移植类库项目**平台不可知的代码。<br /><br /> -此方法通常用于实现业务逻辑的代码。<br />-你可以使用 Visual Basic 或 C#。<br />-API 支持因平台而异。<br />的面向 Windows 8.1 和 Windows Phone 8.1 可移植类库项目支持 Windows 运行时 Api 和 XAML。 这些功能在较旧版本的可移植类库中不可用。<br />-如果需要可以通过使用接口或抽象类抽象处理平台特定的代码。<br /><br /> 有关详细信息，请参见：<br /><br /> -   [可移植类库](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)（MSDN 文章）<br />-   [如何使可移植类库工作为你](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx)（博客文章）<br />-   [可移植类库与 MVVM 配合使用](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)（MSDN 文章）<br />-   [库，面向多个平台的应用程序资源](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)（MSDN 文章）<br />-   [.NET 可移植性分析器](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)（Visual Studio 扩展）|  
|在平台（Windows8.1 和 Windows Phone 8.1 除外）的应用之间共享源代码|**添加为链接**功能。<br /><br /> -此方法非常适用于出于某种原因是这两个应用程序通用的但不可移植的应用程序逻辑。 你可以将此功能用于 C＃ 或 Visual Basic 代码。<br />     例如，Windows Phone 8 和 Windows 8 共享 Windows 运行时 API，但可移植类库不支持这些平台的 Windows 运行时。 你可以使用 `Add as link` 在 Windows Phone 8 应用和面向 Windows 8 的 Windows 应用商店应用之间共享公共 Windows 运行时代码。<br /><br /> 有关详细信息，请参见：<br /><br /> -   [与添加为链接共享代码](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx)（MSDN 文章）<br />-   [如何： 向项目添加现有项](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx)（MSDN 文章）|  
|使用 .NET Framework 代码或从 NET Framework 代码调用 Windows 运行时 API，编写 Windows 应用商店应用|**Windows 运行时 Api**从你的.NET Framework C# 或 Visual Basic 代码，并且使用要创建 Windows 应用商店应用的.NET Framework。 你应该注意这两个平台的 API 差异。 但是，存在帮助你处理这些差异的类。<br /><br /> 有关详细信息，请参见：<br /><br /> -   [.NET framework 支持 Windows 应用商店应用和 Windows 运行时](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)（MSDN 文章）<br />-   [向 Windows 运行时传递 URI](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) （MSDN 文章）<br />-   <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>-->`System.IO.WindowsRuntimeStreamExtensions` （MSDN API 引用页）<br />-   <!--zz <xref:System.WindowsRuntimeSystemExtensions>-->`System.WindowsRuntimeSystemExtensions` （MSDN API 引用页）|  
|构建面向非 Microsoft 平台的 .NET Framework 应用|**可移植类库引用程序集**在.NET Framework 中和 Xamarin 等 Visual Studio 扩展或第三方工具。<br /><br /> 有关详细信息，请参见：<br /><br /> -   [可移植类库现在在所有平台上可用。](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx) （博客文章）<br />-   [Xamarin](http://xamarin.com/visual-studio) （Xamarin 网站）|  
|将 JavaScript 和 HTML 用于跨平台开发|**通用应用模板**在 Visual Studio 2013 中，更新 2 适用于 Windows 8.1 和 Windows Phone 8.1 开发针对 Windows 运行时 Api。 当前，你不能将 .NET Framework API 与 JavaScript 和 HTML 结合使用来开发跨平台应用。<br /><br /> 有关详细信息，请参见：<br /><br /> -   [JavaScript 项目模板](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [移植使用 JavaScript 为 Windows Phone 的 Windows 运行时应用程序](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|
