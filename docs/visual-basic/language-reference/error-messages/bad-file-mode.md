---
title: 错误的文件模式
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935234"
---
# <a name="bad-file-mode"></a>错误的文件模式
在操作文件内容中使用的语句必须是适用于在其中打开该文件的模式。 可能的原因包括：  
  
- 一个`FilePutObject`或`FileGetObject`语句指定的顺序文件。  
  
- 一个`Print`语句指定为访问模式而不打开的文件`Output`或`Append`。  
  
- `Input`语句指定为访问模式而不打开的文件 `Input`  
  
- 试图写入只读文件。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 请确保`FilePutObject`并`FileGetObject`仅指文件供`Random`或`Binary`访问。  
  
- 请确保`Print`指定为打开的文件`Output`或`Append`访问模式。 如果不是，使用不同的语句将数据放在文件中，或重新打开相应的模式中的文件。  
  
- 请确保`Input`指定为打开的文件`Input`。 如果没有，请使用不同的语句将数据放在文件或重新打开相应的模式中的文件。  
  
- 如果写入只读文件时，将该文件的读/写状态更改或不尝试对其进行写入。  
  
- 使用 `My.Computer.FileSystem` 对象中的可用功能。  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.FileSystem>
- [排除故障：读取和写入文本文件](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
