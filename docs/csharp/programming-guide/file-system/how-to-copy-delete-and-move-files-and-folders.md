---
title: "如何：复制、删除和移动文件和文件夹（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 56383873674998fc0d6417a2abf4fa72e498f08f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>如何：复制、删除和移动文件和文件夹（C# 编程指南）
以下示例演示如何从 <xref:System.IO?displayProperty=nameWithType> 命名空间使用 <xref:System.IO.File?displayProperty=nameWithType>、<xref:System.IO.Directory?displayProperty=nameWithType>、<xref:System.IO.FileInfo?displayProperty=nameWithType> 和 <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> 类以同步方式复制、移动和删除文件与文件夹。 这些示例未提供进度栏或其他任何用户界面。 如果希望提供一个标准进度对话框，请参阅[如何：提供文件操作进度对话框](how-to-provide-a-progress-dialog-box-for-file-operations.md)。  
  
 操作多个文件时，请使用 <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> 提供事件，以便可以计算进度。 另一种方法是使用平台调用来调用 Windows Shell 中相应的文件相关方法。 有关如何异步执行这些文件操作的信息，请参阅[异步文件 I/O](https://msdn.microsoft.com/library/kztecsys)。  
  
## <a name="example"></a>示例  
 以下示例演示如何复制文件和目录。  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a>示例  
 以下示例演示如何移动文件和目录。  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a>示例  
 以下示例演示如何删除文件和目录。  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO?displayProperty=nameWithType>  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [文件系统和注册表（C# 编程指南）](index.md)  
 [如何：提供文件操作进度对话框](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [文件和流 I/O](https://msdn.microsoft.com/library/k3352a4t)  
 [通用 I/O 任务](https://msdn.microsoft.com/library/ms404278)
