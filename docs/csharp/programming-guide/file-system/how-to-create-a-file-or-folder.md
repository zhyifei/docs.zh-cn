---
title: 如何：创建文件或文件夹 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: 3163598de5d03bf1691379cddae031841b9865d6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595644"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="ea23f-102">如何：创建文件或文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ea23f-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="ea23f-103">可通过编程方式在计算机上创建文件夹、子文件夹和子文件夹中的文件，并将数据写入文件。</span><span class="sxs-lookup"><span data-stu-id="ea23f-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea23f-104">示例</span><span class="sxs-lookup"><span data-stu-id="ea23f-104">Example</span></span>  
 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 <span data-ttu-id="ea23f-105">如果文件夹已存在，<xref:System.IO.Directory.CreateDirectory%2A> 不执行任何操作，未引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="ea23f-105">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="ea23f-106">但 <xref:System.IO.File.Create%2A?displayProperty=nameWithType> 用新文件替换现有文件。</span><span class="sxs-lookup"><span data-stu-id="ea23f-106">However, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> replaces an existing file with a new file.</span></span> <span data-ttu-id="ea23f-107">本示例使用 `if`-`else` 语句阻止替换现有文件。</span><span class="sxs-lookup"><span data-stu-id="ea23f-107">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="ea23f-108">通过在示例中作出以下更改，可根据具有特定名称的文件是否存在来指定不同的结果。</span><span class="sxs-lookup"><span data-stu-id="ea23f-108">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="ea23f-109">如果该文件不存在，代码就会创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="ea23f-109">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="ea23f-110">如果该文件存在，代码就会将数据追加到该文件中。</span><span class="sxs-lookup"><span data-stu-id="ea23f-110">If such a file exists, the code appends data to that file.</span></span>  
  
- <span data-ttu-id="ea23f-111">指定一个非随机文件名。</span><span class="sxs-lookup"><span data-stu-id="ea23f-111">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- <span data-ttu-id="ea23f-112">用以下代码中的 `using` 语句替换 `if`-`else` 语句。</span><span class="sxs-lookup"><span data-stu-id="ea23f-112">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="ea23f-113">多次运行此示例，验证数据是否每次都添加到了文件中。</span><span class="sxs-lookup"><span data-stu-id="ea23f-113">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="ea23f-114">有关可尝试的 `FileMode` 值，请参阅 <xref:System.IO.FileMode>。</span><span class="sxs-lookup"><span data-stu-id="ea23f-114">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="ea23f-115">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="ea23f-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ea23f-116">文件夹名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="ea23f-116">The folder name is malformed.</span></span> <span data-ttu-id="ea23f-117">例如，它包含非法字符或它仅为空格（<xref:System.ArgumentException> 类）。</span><span class="sxs-lookup"><span data-stu-id="ea23f-117">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="ea23f-118">使用 <xref:System.IO.Path> 类创建有效的路径名。</span><span class="sxs-lookup"><span data-stu-id="ea23f-118">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
- <span data-ttu-id="ea23f-119">要创建的文件夹的父文件夹为只读（<xref:System.IO.IOException> 类）。</span><span class="sxs-lookup"><span data-stu-id="ea23f-119">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="ea23f-120">文件夹名为 `null`<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="ea23f-120">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="ea23f-121">文件夹名过长（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="ea23f-121">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="ea23f-122">文件夹仅为冒号“:”（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="ea23f-122">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ea23f-123">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="ea23f-123">.NET Framework Security</span></span>  
 <span data-ttu-id="ea23f-124">可能在部分信任场景中引发 <xref:System.Security.SecurityException> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="ea23f-124">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="ea23f-125">如果没有创建文件夹的权限，则本示例引发 <xref:System.UnauthorizedAccessException> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="ea23f-125">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea23f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea23f-126">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="ea23f-127">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ea23f-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ea23f-128">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ea23f-128">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
