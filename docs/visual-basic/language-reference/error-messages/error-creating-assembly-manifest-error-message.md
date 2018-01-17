---
title: "创建程序集清单时出错：&lt;错误消息&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e88d28ef787eb57b71d94f4ee51c09e9751dbff
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>创建程序集清单时出错：&lt;错误消息&gt;
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器调用程序集链接器（Al.exe，也称作 Alink）生成包含清单的程序集。 该链接器已报告在创建程序集的预发出阶段中出错。  
  
 如果指定的密钥文件或密钥容器有问题，就可能发生错误。 若要对程序集进行完全签名，必须提供包含公钥和私钥信息的有效密钥文件。 若要延迟对程序集的签名，必须选择“仅延迟签名”复选框，并提供包含公钥信息的有效密钥文件。 当程序集为延迟签名时，不需要使用私有密钥。 有关详细信息，请参阅[如何：使用强名称为程序集签名](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)。  
  
 **错误 ID:** BC30140  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查引用的错误信息并参考主题[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。 错误 AL1019 以获取更多的解释和建议  
  
2.  如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用强名称为程序集签名](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [“项目设计器”->“签名”页](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。  
 [与我们交流](/visualstudio/ide/talk-to-us)
