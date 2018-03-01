---
title: "无法发出程序集：&lt;错误消息&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b19b6439d85822c69adac0b3e0e04b2f31299836
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>无法发出程序集：&lt;错误消息&gt;
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器调用程序集链接器 (Al.exe，也称作 Alink) 生成包含清单的程序集与链接器在创建程序集的发出阶段中报告错误。  
  
 **错误 ID:** BC30145  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查引用的错误信息并参考主题[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。 以获得进一步的解释和建议。  
  
2.  请尝试手动签名程序集使用[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)或[Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)。  
  
3.  如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。  
  
### <a name="to-sign-the-assembly-manually"></a>手动对程序集进行签名  
  
1.  使用 [Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)) 创建公钥/私钥对文件。  
  
     此文件的扩展名为 .snk。  
  
2.  从项目中删除生成错误的 COM 引用。  
  
3.  从 Windows**启动**菜单上，指向**程序**，指向**Microsoft Visual Studio 2008**，指向**Visual Studio Tools**，和然后单击**Visual Studio 2008 命令提示**。  
  
4.  移动到要放置程序集包装的目录。  
  
5.  键入以下代码。  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     下面是你可能会输入的代码的示例。  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     如果路径或文件包含空格，则使用双引号 (")。  
  
6.  在 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 中，添加对刚创建的文件的 .NET 程序集引用。  
  
## <a name="see-also"></a>请参阅  
 
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。  
 [Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md))  
 [如何：创建公钥/私钥对](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [与我们交流](/visualstudio/ide/talk-to-us)
