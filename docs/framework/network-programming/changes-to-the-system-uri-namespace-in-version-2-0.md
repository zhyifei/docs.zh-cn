---
title: "对 2.0 版中的 System.Uri 命名空间的更改 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 对 2.0 版中的 System.Uri 命名空间的更改
些许更改对 <xref:System.Uri?displayProperty=fullName> 选件类。  这些更改已修复不正确的行为，增强的可用性，并增强安全性。  
  
## 过时并已弃用的成员  
 构造函数:  
  
-   有一个 `dontEscape`参数的构造函数。  
  
 方法:  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## 更改  
  
-   若要理解没有查询部件的URI方案\(文件， FTP和其他\)， “?”字符总是转义和不被视为 <xref:System.Uri.Query%2A> 部件的开头。  
  
-   对于隐式文件URI \(窗体“c:\\directory\\file @name.txt”\)，片段字符\(“&#124;”\)始终进行转义，除非完全unescaping请求或 <xref:System.Uri.LocalPath%2A> 是 `true`。  
  
-   UNC主机名支持中移除;表示的国际主机名IDN规范采用。  
  
-   <xref:System.Uri.LocalPath%2A> 始终返回一个完全非转义字符串。  
  
-   <xref:System.Uri.ToString%2A> 不取消每个转义“%”， “? ”或“&#124;”字符。  
  
-   <xref:System.Uri.Equals%2A> 在相等性检查现在包含 <xref:System.Uri.Query%2A> 部件。  
  
-   运算符“\=\=”和“\! \=”与 <xref:System.Uri.Equals%2A> 被重写并链接到方法。  
  
-   <xref:System.Uri.IsLoopback%2A> 现在导致一致的结果。  
  
-   URI “`file:///path`”不再转换为“file:\/\/path”。  
  
-   “&#124;”现在被标识为主机名结束符。  即“http:\/\/consoto.com\#fragment”现在转换为“http:\/\/contoso.com\/\#fragment”。  
  
-   bug，当将一基URI与片段已修复。  
  
-   在 <xref:System.Uri.HostNameType%2A> 的bug进行修复。  
  
-   在分析的NNTP的bug进行修复。  
  
-   窗体 HTTP:contoso.com 的 URI 引发分析异常。  
  
-   在URI的正确结构处理userinfo。  
  
-   URI路径压缩是固定的，以便一中断的URI不能遍历在根上的文件系统。  
  
## 请参阅  
 <xref:System.Uri?displayProperty=fullName>