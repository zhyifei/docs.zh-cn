---
title: Windows 系统中的文件路径格式
ms.date: 06/28/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, long paths
- long paths
- path formats, Windows
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecaae9e1af359ead1c15a9e431eac21e41040efe
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835819"
---
# <a name="file-path-formats-on-windows-systems"></a><span data-ttu-id="a4068-102">Windows 系统中的文件路径格式</span><span class="sxs-lookup"><span data-stu-id="a4068-102">File path formats on Windows systems</span></span>

<span data-ttu-id="a4068-103"><xref:System.IO> 命名空间中很多类型的成员都包括 `path` 参数，让你可以指定指向某个文件系统资源的绝对路径或相对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-103">Members of many of the types in the <xref:System.IO> namespace include a `path` parameter that lets you specify an absolute or relative path to a file system resource.</span></span> <span data-ttu-id="a4068-104">此路径随后会传递至 [Windows 文件系统 API](/windows/desktop/fileio/file-systems)。</span><span class="sxs-lookup"><span data-stu-id="a4068-104">This path is then passed to [Windows file system APIs](/windows/desktop/fileio/file-systems).</span></span> <span data-ttu-id="a4068-105">本主题讨论可在 Windows 系统上使用的文件路径格式。</span><span class="sxs-lookup"><span data-stu-id="a4068-105">This topic discusses the formats for file paths that you can use on Windows systems.</span></span>

## <a name="traditional-dos-paths"></a><span data-ttu-id="a4068-106">传统 DOS 路径</span><span class="sxs-lookup"><span data-stu-id="a4068-106">Traditional DOS paths</span></span>

<span data-ttu-id="a4068-107">标准的 DOS 路径可由以下三部分组成：</span><span class="sxs-lookup"><span data-stu-id="a4068-107">A standard DOS path can consist of three components:</span></span>

- <span data-ttu-id="a4068-108">卷号或驱动器号，后跟卷分隔符 (`:`)。</span><span class="sxs-lookup"><span data-stu-id="a4068-108">A volume or drive letter followed by the volume separator (`:`).</span></span>
- <span data-ttu-id="a4068-109">目录名称。</span><span class="sxs-lookup"><span data-stu-id="a4068-109">A directory name.</span></span> <span data-ttu-id="a4068-110">[目录分隔符](<xref:System.IO.Path.DirectorySeparatorChar>)用来分隔嵌套目录层次结构中的子目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-110">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates subdirectories within the nested directory hierarchy.</span></span>
- <span data-ttu-id="a4068-111">可选的文件名。</span><span class="sxs-lookup"><span data-stu-id="a4068-111">An optional filename.</span></span> <span data-ttu-id="a4068-112">[目录分隔符](<xref:System.IO.Path.DirectorySeparatorChar>)用来分隔文件路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="a4068-112">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates the file path and the filename.</span></span>

<span data-ttu-id="a4068-113">如果以上三项都存在，则为绝对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-113">If all three components are present, the path is absolute.</span></span> <span data-ttu-id="a4068-114">如未指定卷号或驱动器号，且目录名称的开头是[目录分隔符](<xref:System.IO.Path.DirectorySeparatorChar>)，则路径属于当前驱动器根路径上的相对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-114">If no volume or drive letter is specified and the directory names begins with the [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>), the path is relative from the root of the current drive.</span></span> <span data-ttu-id="a4068-115">否则路径相对于当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-115">Otherwise, the path is relative to the current directory.</span></span> <span data-ttu-id="a4068-116">下表显示了一些可能出现的目录和文件路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-116">The following table shows some possible directory and file paths.</span></span>

|<span data-ttu-id="a4068-117">路径</span><span class="sxs-lookup"><span data-stu-id="a4068-117">Path</span></span>  |<span data-ttu-id="a4068-118">说明</span><span class="sxs-lookup"><span data-stu-id="a4068-118">Description</span></span>  |
| -- | -- |
| `C:\Documents\Newsletters\Summer2018.pdf` | <span data-ttu-id="a4068-119">C: 盘根路径上的绝对文件路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-119">An absolute file path from the root of drive C:</span></span> |
| `\Program Files\Custom Utilities\StringFinder.exe` | <span data-ttu-id="a4068-120">当前驱动器根路径上的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-120">An absolute path from the root of the current drive.</span></span> |
| `2018\January.xlsx` | <span data-ttu-id="a4068-121">指向当前目录的子目录中的文件的相对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-121">A relative path to a file in a subdirectory of the current directory.</span></span> |
| `..\Publications\TravelBrochure.pdf` | <span data-ttu-id="a4068-122">指向当前目录的同级目录中的文件的相对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-122">A relative path to file in a directory that is a peer of the current directory.</span></span> |
| `C:\Projects\apilibrary\apilibrary.sln` | <span data-ttu-id="a4068-123">指向 C: 盘根路径中的文件的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-123">An absolute path to a file from the root of drive C:</span></span> |
| `C:Projects\apilibrary\apilibrary.sln` | <span data-ttu-id="a4068-124">C: 盘当前目录上的相对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-124">A relative path from the current directory of the C: drive.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="a4068-125">请注意最后两个路径之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a4068-125">Note the difference between the last two paths.</span></span> <span data-ttu-id="a4068-126">两者都指定了可选的卷说明符（均为“C:”），但前者以所指定卷的根开头，而后者不是。</span><span class="sxs-lookup"><span data-stu-id="a4068-126">Both specify the optional volume specifier (C: in both cases), but the first begins with the root of the specified volume, whereas the second does not.</span></span> <span data-ttu-id="a4068-127">结果，前者表示 C: 盘根目录上的绝对路径，而后者表示 C: 盘当前目录上的相对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-127">As result, the first is an absolute path from the root directory of drive C:, whereas the second is a relative path from the current directory of drive C:.</span></span> <span data-ttu-id="a4068-128">应使用前者时使用了后者是涉及 Windows 文件路径的 bug 的常见原因。</span><span class="sxs-lookup"><span data-stu-id="a4068-128">Use of the second form when the first is intended is a common source of bugs that involve Windows file paths.</span></span>

<span data-ttu-id="a4068-129">可以通过调用 <xref:System.IO.Path.IsPathFullyQualified%2A?displayProperty=nameWthType> 方法来确定文件路径是否完全限定（即是说，该路径独立于当前目录，且在当前目录更改时不发生变化）。</span><span class="sxs-lookup"><span data-stu-id="a4068-129">You can determine whether a file path is fully qualified (that is, it the path is independent of the current directory and does not change when the current directory changes) by calling the <xref:System.IO.Path.IsPathFullyQualified%2A?displayProperty=nameWthType> method.</span></span> <span data-ttu-id="a4068-130">请注意，如果解析的路径始终指向同样的位置，那么此类路径可以包括相对目录段（`.` 和 `..`），而同时依然是完全限定的。</span><span class="sxs-lookup"><span data-stu-id="a4068-130">Note that such a path can include relative directory segments (`.` and `..`) and still be fully qualified if the resolved path always points to the same location.</span></span>

<span data-ttu-id="a4068-131">以下示例演示绝对路径和相对路径之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a4068-131">The following example illustrates the difference between absolute and relative paths.</span></span> <span data-ttu-id="a4068-132">假定存在目录 D:\FY2018\，且在运行该示例之前还没有通过命令提示符为 D:\ 设置任何当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-132">It assumes that the directory D:\FY2018\ exists, and that you haven't set any curent directory for D:\ from the command prompt before running the example.</span></span>

[!code-csharp[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/cs/paths.cs)]
[!code-vb[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/vb/paths.vb)]

## <a name="unc-paths"></a><span data-ttu-id="a4068-133">UNC 路径</span><span class="sxs-lookup"><span data-stu-id="a4068-133">UNC paths</span></span>

<span data-ttu-id="a4068-134">通用命名约定 (UNC) 路径，用于访问网络资源，具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="a4068-134">Universal naming convention (UNC) paths, which are used to access network resources, have the following format:</span></span>

- <span data-ttu-id="a4068-135">一个以 \\\\ 开头的服务器名或主机名。</span><span class="sxs-lookup"><span data-stu-id="a4068-135">A server or host name, which is prefaced by \\\\.</span></span> <span data-ttu-id="a4068-136">服务器名称可以为 NetBIOS 计算机名称或者 IP/FQDN 地址（支持 IPv4 和 IPv6）。</span><span class="sxs-lookup"><span data-stu-id="a4068-136">The server name can be a NetBIOS machine name or an IP/FQDN address (IPv4 as well as v6 are supported).</span></span>
- <span data-ttu-id="a4068-137">共享名，使用 \\ 将其与主机名分隔开。</span><span class="sxs-lookup"><span data-stu-id="a4068-137">A share name, which is separated from the host name by \\.</span></span> <span data-ttu-id="a4068-138">服务器名和共享名共同组成了卷。</span><span class="sxs-lookup"><span data-stu-id="a4068-138">Together, the server and share name make up the volume.</span></span>
- <span data-ttu-id="a4068-139">目录名称。</span><span class="sxs-lookup"><span data-stu-id="a4068-139">A directory name.</span></span> <span data-ttu-id="a4068-140">[目录分隔符](<xref:System.IO.Path.DirectorySeparatorChar>)用来分隔嵌套目录层次结构中的子目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-140">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates subdirectories within the nested directory hierarchy.</span></span>
- <span data-ttu-id="a4068-141">可选的文件名。</span><span class="sxs-lookup"><span data-stu-id="a4068-141">An optional filename.</span></span> <span data-ttu-id="a4068-142">[目录分隔符](<xref:System.IO.Path.DirectorySeparatorChar>)用来分隔文件路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="a4068-142">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates the file path and the filename.</span></span>

<span data-ttu-id="a4068-143">以下是一些 UNC 路径的示例：</span><span class="sxs-lookup"><span data-stu-id="a4068-143">The following are some examples of UNC paths:</span></span>

|<span data-ttu-id="a4068-144">路径</span><span class="sxs-lookup"><span data-stu-id="a4068-144">Path</span></span>  |<span data-ttu-id="a4068-145">说明</span><span class="sxs-lookup"><span data-stu-id="a4068-145">Description</span></span>  |
| -- | -- |
| `\\system07\C$\` | <span data-ttu-id="a4068-146">`system07` 上 C: 盘的根目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-146">The root directory of the C: drive on `system07`.</span></span> |
| `\\Server2\Share\Test\Foo.txt` | <span data-ttu-id="a4068-147">\\\\Server2\\Share 卷的测试目录中的 Foo.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="a4068-147">The Foo.txt file in the Test directory of the \\\\Server2\\Share volume.</span></span>|

<span data-ttu-id="a4068-148">UNC 路径必须始终是完全限定的。</span><span class="sxs-lookup"><span data-stu-id="a4068-148">UNC paths must always be fully qualified.</span></span> <span data-ttu-id="a4068-149">它们可以包括相对目录段（`.` 和 `..`），但是这些目录段必须是完全限定的路径的一部分。</span><span class="sxs-lookup"><span data-stu-id="a4068-149">They can include relative directory segments (`.` and `..`), but these must be part of a fully qualified path.</span></span> <span data-ttu-id="a4068-150">只能通过将 UNC 路径映射至驱动器号来使用相对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-150">You can use relative paths only by mapping a UNC path to a drive letter.</span></span>

## <a name="dos-device-paths"></a><span data-ttu-id="a4068-151">DOS 设备路径</span><span class="sxs-lookup"><span data-stu-id="a4068-151">DOS device paths</span></span>

<span data-ttu-id="a4068-152">Windows 操作系统有一个指向所有资源（包括文件）的统一对象模型。</span><span class="sxs-lookup"><span data-stu-id="a4068-152">The Windows operating system has a unified object model that points to all resources, including files.</span></span> <span data-ttu-id="a4068-153">可从控制台窗口访问这些对象路径；并通过旧版 DOS 和 UNC 路径映射到的符号链接的特殊文件，将这些对象路径公开至 Win32 层。</span><span class="sxs-lookup"><span data-stu-id="a4068-153">These object paths are accessible from the console window and are exposed to the Win32 layer through a special folder of symbolic links that legacy DOS and UNC paths are mapped to.</span></span> <span data-ttu-id="a4068-154">此特殊文件夹可通过 DOS 设备路径语法（以下任一）进行访问：</span><span class="sxs-lookup"><span data-stu-id="a4068-154">This special folder is accessed via the DOS device path syntax, which is one of:</span></span>

`\\.\C:\Test\Foo.txt`  
`\\?\C:\Test\Foo.txt`

> [!NOTE]
> <span data-ttu-id="a4068-155">从 NET Core 1.1 和 .NET Framework 4.6.2 开始，运行在 Windows 上的 .NET 实现支持 DOS 设备路径语法。</span><span class="sxs-lookup"><span data-stu-id="a4068-155">DOS device path syntax is supported on .NET implementations running on Windows starting with .NET Core 1.1 and .NET Framework 4.6.2.</span></span>

<span data-ttu-id="a4068-156">DOS 设备路径由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="a4068-156">The DOS device path consists of the following components:</span></span>

- <span data-ttu-id="a4068-157">设备路径说明符（`\\.\` 或 `\\?\`），它将路径标识为 DOS 设备路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-157">The device path specifier (`\\.\` or `\\?\`), which identifies the path as a DOS device path.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a4068-158">.NET Core 的所有版本以及从 4.6.2 开始的 .NET Framework 版本都支持 `\\?\`。</span><span class="sxs-lookup"><span data-stu-id="a4068-158">The `\\?\` is supported in all versions of .NET Core and in the .NET Framework starting with version 4.6.2.</span></span>
   
- <span data-ttu-id="a4068-159">指向“真正”设备对象（这里是 C:）的符号链接。</span><span class="sxs-lookup"><span data-stu-id="a4068-159">A symbolic link to the "real" device object (C: in this case).</span></span>

   <span data-ttu-id="a4068-160">设备路径说明符后的第一个 DOS 设备路径段标识了卷或驱动器。</span><span class="sxs-lookup"><span data-stu-id="a4068-160">The first segment of the DOS device path after the device path specifier identifies the volume or drive.</span></span> <span data-ttu-id="a4068-161">（例如，`\\?\C:\` 和 `\\.\BootPartition\`。）</span><span class="sxs-lookup"><span data-stu-id="a4068-161">(For example, `\\?\C:\` and `\\.\BootPartition\`.)</span></span>

   <span data-ttu-id="a4068-162">UNC 有个特定的链接，很自然地名为 `UNC`。</span><span class="sxs-lookup"><span data-stu-id="a4068-162">There is a specific link for UNCs that is called, not surprisingly, `UNC`.</span></span> <span data-ttu-id="a4068-163">例如:</span><span class="sxs-lookup"><span data-stu-id="a4068-163">For example:</span></span>

  `\\.\UNC\Server\Share\Test\Foo.txt`  
  `\\?\UNC\Server\Share\Test\Foo.txt`

    <span data-ttu-id="a4068-164">对于设备 UNC，服务器/共享部分构成了卷。</span><span class="sxs-lookup"><span data-stu-id="a4068-164">For device UNCs, the server/share portion is forms the volume.</span></span> <span data-ttu-id="a4068-165">例如，在 `\\?\server1\e:\utilities\\filecomparer\` 中，服务器/共享部分是 server1\utilities。</span><span class="sxs-lookup"><span data-stu-id="a4068-165">For example, in `\\?\server1\e:\utilities\\filecomparer\`, the server/share portion is server1\utilities.</span></span> <span data-ttu-id="a4068-166">使用相对目录段调用 <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> 等方法时，这一点非常重要；决不可能越过卷。</span><span class="sxs-lookup"><span data-stu-id="a4068-166">This is significant when calling a method such as <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> with relative directory segments; it is never possible to navigate past the volume.</span></span> 

<span data-ttu-id="a4068-167">DOS 设备路径通过定义进行完全限定。</span><span class="sxs-lookup"><span data-stu-id="a4068-167">DOS device paths are fully qualified by definition.</span></span> <span data-ttu-id="a4068-168">不允许使用相对目录段（`.` 和 `..`）。</span><span class="sxs-lookup"><span data-stu-id="a4068-168">Relative directory segments (`.` and `..`) are not allowed.</span></span> <span data-ttu-id="a4068-169">也不会包含当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-169">Current directories never enter into their usage.</span></span>

## <a name="example-ways-to-refer-to-the-same-file"></a><span data-ttu-id="a4068-170">示例:引用同一个文件的方法</span><span class="sxs-lookup"><span data-stu-id="a4068-170">Example: Ways to refer to the same file</span></span>

<span data-ttu-id="a4068-171">以下示例演示了一些方法，以此可在使用 <xref:System.IO> 命名空间中的 API 时引用文件。</span><span class="sxs-lookup"><span data-stu-id="a4068-171">The following example illustrates some of the ways in which you can refer to a file when using the APIs in the <xref:System.IO> namespace.</span></span> <span data-ttu-id="a4068-172">该示例实例化 <xref:System.IO.FileInfo> 对象，并使用它的 <xref:System.IO.FileInfo.Name> 和 <xref:System.IO.FileInfo.Length> 属性来显示文件名以及文件长度。</span><span class="sxs-lookup"><span data-stu-id="a4068-172">The example instantiates a <xref:System.IO.FileInfo> object and uses its <xref:System.IO.FileInfo.Name> and <xref:System.IO.FileInfo.Length> properties to display the filename and the length of the file.</span></span>

[!code-csharp[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/cs/file-refs.cs)]
[!code-vb[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/vb/file-refs.vb)]

## <a name="path-normalization"></a><span data-ttu-id="a4068-173">路径规范化</span><span class="sxs-lookup"><span data-stu-id="a4068-173">Path normalization</span></span>

<span data-ttu-id="a4068-174">几乎所有传递至 Windows API 的路径都经过规范化。</span><span class="sxs-lookup"><span data-stu-id="a4068-174">Almost all paths passed to Windows APIs are normalized.</span></span> <span data-ttu-id="a4068-175">规范化过程中，Windows 执行了以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a4068-175">During normalization, Windows performs the following steps:</span></span>

- <span data-ttu-id="a4068-176">识别路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-176">Identifies the path.</span></span>
- <span data-ttu-id="a4068-177">将当前目录应用于部分限定（相对）路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-177">Applies the current directory to partially qualified (relative) paths.</span></span>
- <span data-ttu-id="a4068-178">规范化组件和目录分隔符。</span><span class="sxs-lookup"><span data-stu-id="a4068-178">Canonicalizes component and directory separators.</span></span>
- <span data-ttu-id="a4068-179">评估相对目录组件（当前目录是 `.`，父目录是 `..`）。</span><span class="sxs-lookup"><span data-stu-id="a4068-179">Evaluates relative directory components (`.` for the current directory and `..` for the parent directory).</span></span>
- <span data-ttu-id="a4068-180">剪裁特定字符。</span><span class="sxs-lookup"><span data-stu-id="a4068-180">Trims certain characters.</span></span>

<span data-ttu-id="a4068-181">这种规范化隐式进行，若想显式进行规范化，可以调用 <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType> 方法，这会包装对 [GetFullPathName() 函数](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)的调用。</span><span class="sxs-lookup"><span data-stu-id="a4068-181">This normalization happens implicitly, but you can do it explicitly by calling the <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType> method, which wraps a call to the  [GetFullPathName() function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea).</span></span> <span data-ttu-id="a4068-182">还可以使用 P/Invoke 直接调用 Windows [GetFullPathName() 函数](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)。</span><span class="sxs-lookup"><span data-stu-id="a4068-182">You can also call the Windows [GetFullPathName() function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) directly using P/Invoke.</span></span>

### <a name="identifying-the-path"></a><span data-ttu-id="a4068-183">识别路径</span><span class="sxs-lookup"><span data-stu-id="a4068-183">Identifying the path</span></span>

<span data-ttu-id="a4068-184">路径规范化的第一步就是识别路径类型。</span><span class="sxs-lookup"><span data-stu-id="a4068-184">The first step in path normalization is identifying the type of path.</span></span> <span data-ttu-id="a4068-185">路径归为以下几个类别之一：</span><span class="sxs-lookup"><span data-stu-id="a4068-185">Paths fall into one of a few categories:</span></span>

- <span data-ttu-id="a4068-186">它们是设备路径；就是说，它们的开头是两个分隔符和一个问号或句点（`\\?` 或 `\\.`）。</span><span class="sxs-lookup"><span data-stu-id="a4068-186">They are device paths; that is, they begin with two separators and a question mark or period (`\\?` or `\\.`).</span></span>
- <span data-ttu-id="a4068-187">它们是 UNC 路径；就是说，它们的开头是两个分隔符，没有问号或句点。</span><span class="sxs-lookup"><span data-stu-id="a4068-187">They are UNC paths; that is, they begin with two separators without a question mark or period.</span></span> 
- <span data-ttu-id="a4068-188">它们是完全限定的 DOS 路径；就是说，它们的开头是驱动器号、卷分隔符和组件分隔符 (`C:\`)。</span><span class="sxs-lookup"><span data-stu-id="a4068-188">They are fully qualified DOS paths; that is, they begin with a drive letter, a volume separator, and a component separator (`C:\`).</span></span>
- <span data-ttu-id="a4068-189">它们指定旧设备（`CON`、`LPT1`）。</span><span class="sxs-lookup"><span data-stu-id="a4068-189">They designate a legacy device (`CON`, `LPT1`).</span></span>
- <span data-ttu-id="a4068-190">它们相对于当前驱动器的根路径；就是说，它们的开头是单个组件分隔符 (`\`)。</span><span class="sxs-lookup"><span data-stu-id="a4068-190">They are relative to the root of the current drive; that is, they begin with a single component separator (`\`).</span></span>
- <span data-ttu-id="a4068-191">它们相对于指定驱动器的当前目录；就是说，它们的开头是驱动器号和卷分隔符，而没有组件分隔符 (`C:`)。</span><span class="sxs-lookup"><span data-stu-id="a4068-191">They are relative to the current directory of a specified drive; that is, they begin with a drive letter, a volume separator, and no component separator (`C:`).</span></span>
- <span data-ttu-id="a4068-192">它们相对于当前目录；就是说，它们的开头是上述情况以外的任何内容 (`temp\testfile.txt`)。</span><span class="sxs-lookup"><span data-stu-id="a4068-192">They are relative to the current directory; that is, they begin with anything else (`temp\testfile.txt`).</span></span>

<span data-ttu-id="a4068-193">路径的类型决定是否以某种方式应用当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-193">The type of the path determines whether or not a current directory is applied in some way.</span></span> <span data-ttu-id="a4068-194">还决定该路径的“根”是什么。</span><span class="sxs-lookup"><span data-stu-id="a4068-194">It also determines what the "root" of the path is.</span></span>

### <a name="handling-legacy-devices"></a><span data-ttu-id="a4068-195">处理旧设备</span><span class="sxs-lookup"><span data-stu-id="a4068-195">Handling legacy devices</span></span>

<span data-ttu-id="a4068-196">如果路径是旧版 DOS 设备（例如 `CON``COM1` 或 `LPT1`），则会转换为设备路径（方法是在其前面追加 `\\.\`）并返回。</span><span class="sxs-lookup"><span data-stu-id="a4068-196">If the path is a legacy DOS device such as `CON`, `COM1`, or `LPT1`, it is converted into a device path by prepending `\\.\` and returned.</span></span> 

<span data-ttu-id="a4068-197">开头为旧设备名的路径始终被 <xref:System.IO.Path.GetFullPath(System.String)?displayProperty=nameWithType> 方法解释为旧设备。</span><span class="sxs-lookup"><span data-stu-id="a4068-197">A path that begins with a legacy device name is always interpreted as a legacy device by the <xref:System.IO.Path.GetFullPath(System.String)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a4068-198">例如，`CON.TXT` 的 DOS 设备路径为 `\\.\CON`，而 `COM1.TXT\file1.txt` 的 DOS 设备路径为 `\\.\COM1`。</span><span class="sxs-lookup"><span data-stu-id="a4068-198">For example, the DOS device path for `CON.TXT` is `\\.\CON`, and the DOS device path for `COM1.TXT\file1.txt` is `\\.\COM1`.</span></span>

### <a name="applying-the-current-directory"></a><span data-ttu-id="a4068-199">应用当前目录</span><span class="sxs-lookup"><span data-stu-id="a4068-199">Applying the current directory</span></span>

<span data-ttu-id="a4068-200">如果路径非完全限定，Windows 会向其应用当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-200">If a path isn't fully qualified, Windows applies the current directory to it.</span></span> <span data-ttu-id="a4068-201">不会向 UNC 和设备路径应用当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-201">UNCs and device paths do not have the current directory applied.</span></span> <span data-ttu-id="a4068-202">带有分隔符 C:\\ 的完整驱动器也不会。</span><span class="sxs-lookup"><span data-stu-id="a4068-202">Neither does a full drive with separator C:\\.</span></span>

<span data-ttu-id="a4068-203">如果路径的开头是单个组件分隔符，则会应用当前目录中的驱动器。</span><span class="sxs-lookup"><span data-stu-id="a4068-203">If the path starts with a single component separator, the drive from the current directory is applied.</span></span> <span data-ttu-id="a4068-204">例如，如果文件路径是 `\utilities` 且当前目录为 `C:\temp\`，规范化后路径则为 `C:\utilities`。</span><span class="sxs-lookup"><span data-stu-id="a4068-204">For example, if the file path is `\utilities` and the current directory is `C:\temp\`, normalization produces `C:\utilities`.</span></span>

<span data-ttu-id="a4068-205">如果路径开头是驱动器号和卷分隔符，而没有组件分隔符，则应用从命令行界面为指定驱动器设置的最新当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-205">If the path starts with a drive letter, volume separator, and no component separator, the last current directory set from the command shell for the specified drive is applied.</span></span> <span data-ttu-id="a4068-206">如未设置最新当前目录，则只应用驱动器。</span><span class="sxs-lookup"><span data-stu-id="a4068-206">If the last current directory was not set, the drive alone is applied.</span></span> <span data-ttu-id="a4068-207">例如，如果文件路径为 `D:sources`，当前目录为 `C:\Documents\`，且 D: 盘上的最新当前目录为 `D:\sources\`，则结果为 `D:\sources\sources`。</span><span class="sxs-lookup"><span data-stu-id="a4068-207">For example, if the file path is `D:sources`, the current directory is `C:\Documents\`, and the last current directory on drive D: was `D:\sources\`, the result is `D:\sources\sources`.</span></span> <span data-ttu-id="a4068-208">这些“驱动器相对”路径是导致程序和脚本逻辑错误的常见原因。</span><span class="sxs-lookup"><span data-stu-id="a4068-208">These "drive relative" paths are a common source of program and script logic errors.</span></span> <span data-ttu-id="a4068-209">假设以字母和冒号开头的路径不是相对路径，显然是不正确的。</span><span class="sxs-lookup"><span data-stu-id="a4068-209">Assuming that a path beginning with a letter and a colon isn't relative is obviously not correct.</span></span>

<span data-ttu-id="a4068-210">如果路径不是以分隔符开头的，则应用当前驱动器和当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-210">If the path starts with something other than a separator, the current drive and current directory are applied.</span></span> <span data-ttu-id="a4068-211">例如，如果路径是 `filecompare` 且当前目录是 `C:\utilities\`，则结果为 `C:\utilities\filecompare\`。</span><span class="sxs-lookup"><span data-stu-id="a4068-211">For example, if the path is `filecompare` and the current directory is `C:\utilities\`, the result is `C:\utilities\filecompare\`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4068-212">相对路径在多线程应用程序（也就是大多数应用程序）中很危险，因为当前目录是分进程的设置。</span><span class="sxs-lookup"><span data-stu-id="a4068-212">Relative paths are dangerous in multithreaded applications (that is, most applications) because the current directory is a per-process setting.</span></span> <span data-ttu-id="a4068-213">任何线程都能在任何时候更改当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-213">Any thread can change the current directory at any time.</span></span> <span data-ttu-id="a4068-214">从 .NET Core 2.1 开始，可以调用 <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> 方法，从想要据此解析绝对路径的相对路径和基础路径（当前目录）获取绝对路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-214">Starting with .NET Core 2.1, you can call the <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> method to get an absolute path from a relative path and the base path (the current directory) that you want to resolve it against.</span></span> 

### <a name="canonicalizing-separators"></a><span data-ttu-id="a4068-215">规范化分隔符</span><span class="sxs-lookup"><span data-stu-id="a4068-215">Canonicalizing separators</span></span>

<span data-ttu-id="a4068-216">将所有正斜杠 (`/`) 转换为标准的 Windows 分隔符，也就是反斜杠 (`\`)。</span><span class="sxs-lookup"><span data-stu-id="a4068-216">All forward slashes (`/`) are converted into the standard Windows separator, the back slash (`\`).</span></span> <span data-ttu-id="a4068-217">如果存在斜杠，前两个斜杠后面的一系列斜杠都将折叠为一个斜杠。</span><span class="sxs-lookup"><span data-stu-id="a4068-217">If they are present, a series of slashes that follow the first two slashes are collapsed into a single slash.</span></span>

### <a name="evaluating-relative-components"></a><span data-ttu-id="a4068-218">评估相对组件</span><span class="sxs-lookup"><span data-stu-id="a4068-218">Evaluating relative components</span></span>

<span data-ttu-id="a4068-219">处理路径时，会评估所有由一个或两个句点（`.` 或 `..`）组成的组件或分段：</span><span class="sxs-lookup"><span data-stu-id="a4068-219">As the path is processed, any components or segments that are composed of a single or a double period (`.` or `..`) are evaluated:</span></span> 

- <span data-ttu-id="a4068-220">如果是单句点，则删除当前分段，因为它表示当前目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-220">For a single period, the current segment is removed, since it refers to the current directory.</span></span>

- <span data-ttu-id="a4068-221">如果是双句点，则删除当前分段和父级分段，因为双句点表示父级目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-221">For a double period, the current segment and the parent segment are removed, since the double period refers to the parent directory.</span></span>

   <span data-ttu-id="a4068-222">仅当父级目录未越过路径的根时，才删除父级目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-222">Parent directories are only removed if they aren't past the root of the path.</span></span> <span data-ttu-id="a4068-223">路径的根取决于路径的类型。</span><span class="sxs-lookup"><span data-stu-id="a4068-223">The root of the path depends on the type of path.</span></span> <span data-ttu-id="a4068-224">对于 DOS 路径，根是驱动器 (`C:\`)；对于UNC，根是服务器/共享 (`\\Server\Share`)；对于设备路径，则为设备路径前缀（`\\?\` 或 `\\.\`）。</span><span class="sxs-lookup"><span data-stu-id="a4068-224">It is the drive (`C:\`) for DOS paths, the server/share for UNCs (`\\Server\Share`), and the device path prefix for device paths (`\\?\` or `\\.\`).</span></span>

### <a name="trimming-characters"></a><span data-ttu-id="a4068-225">剪裁字符</span><span class="sxs-lookup"><span data-stu-id="a4068-225">Trimming characters</span></span>

<span data-ttu-id="a4068-226">随着分隔符的运行和相对段先遭删除，一些其他字符在规范化过程中也删除了：</span><span class="sxs-lookup"><span data-stu-id="a4068-226">Along with the runs of separators and relative segments removed earlier, some additional characters are removed during normalization:</span></span>

- <span data-ttu-id="a4068-227">如果某段以单个句点结尾，则删除此句点。</span><span class="sxs-lookup"><span data-stu-id="a4068-227">If a segment ends in a single period, that period is removed.</span></span> <span data-ttu-id="a4068-228">（单个或两个句点的段在之前的步骤中已规范化。</span><span class="sxs-lookup"><span data-stu-id="a4068-228">(A segment of a single or double period is normalized in the previous step.</span></span> <span data-ttu-id="a4068-229">三个或更多句点的段未规范化，并且实际上是有效的文件/目录名。）</span><span class="sxs-lookup"><span data-stu-id="a4068-229">A segment of three or more periods is not normalized and is actually a valid file/directory name.)</span></span>

- <span data-ttu-id="a4068-230">如果路径的结尾不是分隔符，则删除所有尾随句点和空格 (U+0020)。</span><span class="sxs-lookup"><span data-stu-id="a4068-230">If the path doesn't end in a separator, all trailing periods and spaces (U+0020) are removed.</span></span> <span data-ttu-id="a4068-231">如果最后的段只是单个或两个句点，则按上述相对组件规则处理。</span><span class="sxs-lookup"><span data-stu-id="a4068-231">If the last segment is simply a single or double period, it falls under the relative components rule above.</span></span> 

   <span data-ttu-id="a4068-232">此规则意味着可以创建以空格结尾的目录名称，方法是在空格后添加结尾分隔符。</span><span class="sxs-lookup"><span data-stu-id="a4068-232">This rule means that you can create a directory name with a trailing space by adding a trailing separator after the space.</span></span>  

   > [!IMPORTANT]
   > <span data-ttu-id="a4068-233">请勿创建以空格结尾的目录名或文件名。</span><span class="sxs-lookup"><span data-stu-id="a4068-233">You should **never** create a directory or filename with a trailing space.</span></span> <span data-ttu-id="a4068-234">如果以空格结尾，则可能难以或者无法访问目录，并且应用程序在尝试处理这样的目录或文件时通常会操作失败。</span><span class="sxs-lookup"><span data-stu-id="a4068-234">Trailing spaces can make it difficult or impossible to access a directory, and applications commonly fail when attempting to handle directories or files whose names include trailing spaces.</span></span>

## <a name="skipping-normalization"></a><span data-ttu-id="a4068-235">跳过规范化</span><span class="sxs-lookup"><span data-stu-id="a4068-235">Skipping normalization</span></span>

<span data-ttu-id="a4068-236">一般来说，任何传递到 Windows API 的路径都会（有效地）传递到 [GetFullPathName 函数](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)并进行规范化。</span><span class="sxs-lookup"><span data-stu-id="a4068-236">Normally, any path passed to a Windows API is (effectively) passed to the [GetFullPathName function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) and normalized.</span></span> <span data-ttu-id="a4068-237">但是有一种很重要的例外情况：以问号（而不是句点）开头的设备路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-237">There is one important exception: a device path that begins with a question mark instead of a period.</span></span> <span data-ttu-id="a4068-238">除非路径确切地以 `\\?\` 开头（注意使用的是规范的反斜杠），否则会对它进行规范化。</span><span class="sxs-lookup"><span data-stu-id="a4068-238">Unless the path starts exactly with `\\?\` (note the use of the canonical backslash), it is normalized.</span></span>

<span data-ttu-id="a4068-239">为什么要跳过规范化过程？</span><span class="sxs-lookup"><span data-stu-id="a4068-239">Why would you want to skip normalization?</span></span> <span data-ttu-id="a4068-240">主要有三方面的原因：</span><span class="sxs-lookup"><span data-stu-id="a4068-240">There are three major reasons:</span></span>

1. <span data-ttu-id="a4068-241">为了访问那些通常无法访问但合法的路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-241">To get access to paths that are normally unavailable but are legal.</span></span> <span data-ttu-id="a4068-242">例如名为 `hidden.` 的文件或目录，这是能访问它的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="a4068-242">A file or directory called `hidden.`, for example, is impossible to access in any other way.</span></span> 

1. <span data-ttu-id="a4068-243">为了在已规范化的情况下通过跳过规范化过程来提升性能。</span><span class="sxs-lookup"><span data-stu-id="a4068-243">To improve performance by skipping normalization if you've already normalized.</span></span>

1. <span data-ttu-id="a4068-244">为了跳过路径长度的 `MAX_PATH` 检查以允许多于 259 个字符的路径（仅在 .NET Framework 上）。</span><span class="sxs-lookup"><span data-stu-id="a4068-244">On the .NET Framework only, to skip the `MAX_PATH` check for path length to allow for paths that are greater than 259 characters.</span></span> <span data-ttu-id="a4068-245">大多数 API 都允许这一点，也有一些例外情况。</span><span class="sxs-lookup"><span data-stu-id="a4068-245">Most APIs allow this, with some exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="a4068-246">.NET Core 显式处理长路径，且不执行 `MAX_PATH` 检查。</span><span class="sxs-lookup"><span data-stu-id="a4068-246">.NET Core handles long paths implicitly and does not perform a `MAX_PATH` check.</span></span> <span data-ttu-id="a4068-247">`MAX_PATH` 检查只适用于 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="a4068-247">The `MAX_PATH` check applies only to the .NET Framework.</span></span>

<span data-ttu-id="a4068-248">跳过规范化和路径上限检查是两种设备路径语法之间唯一的区别；除此以外它们是完全相同的。</span><span class="sxs-lookup"><span data-stu-id="a4068-248">Skipping normalization and max path checks is the only difference between the two device path syntaxes; they are otherwise identical.</span></span> <span data-ttu-id="a4068-249">请谨慎地选择跳过规范化，因为很容易就会创建出“一般”应用程序难以处理的路径。</span><span class="sxs-lookup"><span data-stu-id="a4068-249">Be careful with skipping normalization, since you can easily create paths that are difficult for "normal" applications to deal with.</span></span>

<span data-ttu-id="a4068-250">如果将开头为 `\\?\` 的路径显式地传递至 [GetFullPathName 函数](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)，则依然会对它们进行规范化。</span><span class="sxs-lookup"><span data-stu-id="a4068-250">Paths that start with `\\?\` are still normalized if you explicitly pass them to the [GetFullPathName function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea).</span></span>

<span data-ttu-id="a4068-251">请注意，可将超过 `MAX_PATH` 字符数的路径传递至 [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)，前提是该路径不含 `\\?\`。</span><span class="sxs-lookup"><span data-stu-id="a4068-251">Note that you can paths of more than `MAX_PATH` characters to [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) without `\\?\`.</span></span> <span data-ttu-id="a4068-252">支持任意长度的路径，只要其字符串大小在 Windows 能处理的范围内。</span><span class="sxs-lookup"><span data-stu-id="a4068-252">It supports arbitrary length paths up to the maximum string size that Windows can handle.</span></span>

## <a name="case-and-the-windows-file-system"></a><span data-ttu-id="a4068-253">大小写和 Windows 文件系统</span><span class="sxs-lookup"><span data-stu-id="a4068-253">Case and the Windows file system</span></span>

<span data-ttu-id="a4068-254">Windows 文件系统有一个让非 Window 用户和开发人员感到困惑的特性，就是路径和目录名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a4068-254">A peculiarity of the Windows file system that non-Windows users and developers find confusing is that path and directory names are case-insensitive.</span></span> <span data-ttu-id="a4068-255">也就是说，目录名和文件名反映的是创建它们时所使用的字符串的大小写。</span><span class="sxs-lookup"><span data-stu-id="a4068-255">That is, directory and file names reflect the casing of the strings used when they are created.</span></span> <span data-ttu-id="a4068-256">例如，名为</span><span class="sxs-lookup"><span data-stu-id="a4068-256">For example, the method call</span></span>

```csharp
Directory.Create("TeStDiReCtOrY");
```

```vb
Directory.Create("TeStDiReCtOrY")
```

<span data-ttu-id="a4068-257">的方法创建名为 TeStDiReCtOrY 的目录。</span><span class="sxs-lookup"><span data-stu-id="a4068-257">creates a directory named TeStDiReCtOrY.</span></span> <span data-ttu-id="a4068-258">如果重命名目录或文件以改变大小写，则目录名或文件名反映的是重命名它们时所使用的字符串的大小写。</span><span class="sxs-lookup"><span data-stu-id="a4068-258">If you rename a directory or file to change its case, the directory or file name reflects the case of the string used when you rename it.</span></span> <span data-ttu-id="a4068-259">例如，以下代码将文件 test.txt 重命名为 Test.txt：</span><span class="sxs-lookup"><span data-stu-id="a4068-259">For example, the following code renames a file named test.txt to Test.txt:</span></span>

[!code-csharp[case-and-renaming](~/samples/snippets/standard/io/file-names/cs/rename.cs)]
[!code-vb[case-and-renaming](~/samples/snippets/standard/io/file-names/vb/rename.vb)]

<span data-ttu-id="a4068-260">但是比较目录名和文件名时不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a4068-260">However, directory and file name comparisons are case-insensitive.</span></span> <span data-ttu-id="a4068-261">如果搜索名为“test.txt”的文件，.NET 文件系统 API 会在比较时忽略大小写问题。</span><span class="sxs-lookup"><span data-stu-id="a4068-261">If you search for a file named "test.txt", .NET file system APIs ignore case in the comparison.</span></span> <span data-ttu-id="a4068-262">Test.txt、TEST.TXT、test.TXT 和其他任何大写和小写的字母组合都会成为“test.txt”的匹配项。</span><span class="sxs-lookup"><span data-stu-id="a4068-262">Test.txt, TEST.TXT, test.TXT, and any other combination of upper- and lowercase letters will match "test.txt".</span></span>
