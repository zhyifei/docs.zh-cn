---
title: "Cert2spc.exe（软件发行者证书测试工具） | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Cert2spc.exe"
  - "证书, 发行者证书"
  - "发行者证书"
  - "“软件发行者证书测试”工具"
  - "SPC"
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Cert2spc.exe（软件发行者证书测试工具）
软件发行者证书测试工具从一个或多个 X.509 证书创建软件发行者证书 \(SPC\)。  Cert2spc.exe 仅用于测试目的。  可以从证书颁发机构（如 VeriSign 或 Thawte）获得有效 SPC。  有关创建 X.509 证书的更多信息，请参见[Makecert.exe（证书创建工具）](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)。  
  
 此工具会自动随 Visual Studio 一起安装。  若要运行此工具，请使用开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。  有关详细信息，请参阅 [命令提示符](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。  
  
 在命令提示符处，键入以下内容：  
  
## 语法  
  
```  
  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### 参数  
  
|参数|说明|  
|--------|--------|  
|`certN.cer`|要包含在 SPC 文件中的 X.509 证书的名称。  可以指定用空格分隔的多个名称。|  
|`crlN.crl`|要包含在 SPC 文件中的证书吊销列表的名称。  可以指定用空格分隔的多个名称。|  
|`outputSPCfile.spc`|将包含 X.509 证书的 PKCS \#7 对象的名称。|  
  
|选项|说明|  
|--------|--------|  
|**\/?**|显示该工具的命令语法和选项。|  
  
## 示例  
 下面的命令从 `myCertificate.cer` 创建一个 SPC 并将其放入 `mySPCFile.spc`。  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 下面的命令从 `oneCertificate.cer` 和 `twoCertificate.cer` 创建一个 SPC，并将其放入 `mySPCFile.spc`。  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## 请参阅  
 [工具](../../../docs/framework/tools/index.md)   
 [Makecert.exe（证书创建工具）](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [命令提示符](../../../docs/framework/tools/developer-command-prompt-for-vs.md)