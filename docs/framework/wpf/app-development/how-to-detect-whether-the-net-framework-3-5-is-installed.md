---
title: 如何：检测是否安装了.NET Framework 3.5
ms.date: 03/30/2017
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
ms.openlocfilehash: 2f3e3077f78aed90f4e213d61267131019664fdb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378758"
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="a45a9-102">如何：检测是否安装了.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="a45a9-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="a45a9-103">管理员可部署的系统上的 Windows Presentation Foundation (WPF) 应用程序之前[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]，它们必须先确认[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]运行时已存在。</span><span class="sxs-lookup"><span data-stu-id="a45a9-103">Before administrators can deploy Windows Presentation Foundation (WPF) applications on a system that targets the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], they must first confirm that the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] runtime is present.</span></span> <span data-ttu-id="a45a9-104">本主题提供了编写的脚本在 HTML/JavaScript，管理员可以用于确定是否[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]系统上存在。</span><span class="sxs-lookup"><span data-stu-id="a45a9-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a45a9-105">有关更多详细信息上安装、 部署和检测[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]，请参阅[安装面向开发人员的.NET Framework](../../install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="a45a9-105">For more detailed information on installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a45a9-106">示例</span><span class="sxs-lookup"><span data-stu-id="a45a9-106">Example</span></span>  
 <span data-ttu-id="a45a9-107">当[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]是安装，MSI 向".NET CLR"和版本号的 UserAgent 字符串。</span><span class="sxs-lookup"><span data-stu-id="a45a9-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="a45a9-108">下面的示例演示一个简单的 HTML 页面中嵌入的脚本。</span><span class="sxs-lookup"><span data-stu-id="a45a9-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="a45a9-109">脚本搜索用户代理字符串以确定是否[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]安装，并在搜索结果中显示的状态消息。</span><span class="sxs-lookup"><span data-stu-id="a45a9-109">The script searches the UserAgent string to determine whether the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a45a9-110">此脚本旨在为 Internet 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="a45a9-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="a45a9-111">其他浏览器可能不包括用户代理字符串中的.NET CLR 的信息。</span><span class="sxs-lookup"><span data-stu-id="a45a9-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
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
  
 <span data-ttu-id="a45a9-112">如果为".NET CLR"版本搜索成功，将显示以下类型的状态消息：</span><span class="sxs-lookup"><span data-stu-id="a45a9-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="a45a9-113">否则，将显示以下类型的状态消息：</span><span class="sxs-lookup"><span data-stu-id="a45a9-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="a45a9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a45a9-114">See also</span></span>
- [<span data-ttu-id="a45a9-115">检测是否安装了 .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="a45a9-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
