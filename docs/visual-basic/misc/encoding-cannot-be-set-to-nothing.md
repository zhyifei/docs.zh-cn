---
title: 编码不能设置为 Nothing。
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 30b0b4a29fbdf931aa62263b75d1fa946e87b145
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970321"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>编码不能设置为 Nothing。
尝试读取或写入文件失败，因为已将参数 `encoding` 设置为 `Nothing` ，但需要有效值。  
  
 <xref:System.Text.Encoding> 用于确定写入文件时使用何种编码。 默认为 UTF-8。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 为 `encoding` 参数提供有效值。  
  
## <a name="see-also"></a>请参阅

- [文件编码](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [从文件读取](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [写入文件](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My.Computer.FileSystem.ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My.Computer.FileSystem.WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
