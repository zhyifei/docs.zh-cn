---
title: 如何：检测是否安装了 .NET Framework 3.0
ms.date: 03/30/2017
helpviewer_keywords:
- WinFX Runtime user-agent string
- presence of WPT [WPF], detecting
- detecting WPF presence [WPF]
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
ms.openlocfilehash: 27f856b895f48dc2365a1721dbc90294269899c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947818"
---
# <a name="how-to-detect-whether-the-net-framework-30-is-installed"></a><span data-ttu-id="04b2a-102">如何：检测是否安装了 .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="04b2a-102">How to: Detect Whether the .NET Framework 3.0 Is Installed</span></span>
<span data-ttu-id="04b2a-103">管理员可部署的系统上的 Microsoft.NET Framework 应用程序之前，他们必须首先确认存在的.NET Framework 运行时。</span><span class="sxs-lookup"><span data-stu-id="04b2a-103">Before administrators can deploy Microsoft .NET Framework applications on a system, they must first confirm that the .NET Framework runtime is present.</span></span> <span data-ttu-id="04b2a-104">本主题提供了 HTML/JavaScript 中编写的脚本管理员可用来确定.NET Framework 是否存在的系统上。</span><span class="sxs-lookup"><span data-stu-id="04b2a-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04b2a-105">有关详细安装信息，部署和检测 Microsoft.NET Framework，请参阅中的讨论[部署 Microsoft.NET Framework 版本 3.0](https://go.microsoft.com/fwlink/?LinkId=96739)。</span><span class="sxs-lookup"><span data-stu-id="04b2a-105">For more detailed information on installing, deploying, and detecting the Microsoft .NET Framework, see the discussion in [Deploying Microsoft .NET Framework Version 3.0](https://go.microsoft.com/fwlink/?LinkId=96739).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="detect-the-net-clr-user-agent-string"></a><span data-ttu-id="04b2a-106">检测到".NET CLR"用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="04b2a-106">Detect the ".NET CLR" User-Agent String</span></span>  
 <span data-ttu-id="04b2a-107">安装.NET Framework，MSI 将".NET CLR"和版本号添加到用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="04b2a-107">When .NET Framework is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="04b2a-108">下面的示例演示一个简单的 HTML 页面中嵌入的脚本。</span><span class="sxs-lookup"><span data-stu-id="04b2a-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="04b2a-109">该脚本将搜索用户代理字符串以确定是否安装.NET Framework，并在搜索结果中显示的状态消息。</span><span class="sxs-lookup"><span data-stu-id="04b2a-109">The script searches the UserAgent string to determine whether .NET Framework is installed, and displays a status message on the results of the search.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.0</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.0.04425.00";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.0: "   
          + dotNETRuntimeVersion  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.0."  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="04b2a-110">如果为".NET CLR"版本搜索成功，将显示以下类型的状态消息：</span><span class="sxs-lookup"><span data-stu-id="04b2a-110">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 <span data-ttu-id="04b2a-111">否则，将显示以下类型的状态消息：</span><span class="sxs-lookup"><span data-stu-id="04b2a-111">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`
