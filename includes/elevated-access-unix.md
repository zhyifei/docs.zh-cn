---
ms.openlocfilehash: 85f50b221e7ecb1ebd6fa539894ab7aabed8d362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "67540080"
---
### <a name="install-the-global-tool"></a><span data-ttu-id="e100f-101">安装全局工具</span><span class="sxs-lookup"><span data-stu-id="e100f-101">Install the global tool</span></span>

<span data-ttu-id="e100f-102">应使用 `--tool-path` 选项将包资产安装在受保护的位置。</span><span class="sxs-lookup"><span data-stu-id="e100f-102">Package assets should be installed in a protected location using the `--tool-path` option.</span></span> <span data-ttu-id="e100f-103">这种分离可避免与提升的环境共享受限的用户环境。</span><span class="sxs-lookup"><span data-stu-id="e100f-103">This separation avoids sharing a restricted user environment with an elevated environment.</span></span>

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="e100f-104">将使用权限 `drwxr-xr-x` 创建 `/usr/local/share/dotnet-tools`。</span><span class="sxs-lookup"><span data-stu-id="e100f-104">`/usr/local/share/dotnet-tools` will be created with permission `drwxr-xr-x`.</span></span> <span data-ttu-id="e100f-105">如果该目录已存在，请使用 `ls -l` 命令验证受限的用户是否无权编辑该目录。</span><span class="sxs-lookup"><span data-stu-id="e100f-105">If the directory already exists, use the `ls -l` command to verify the restricted user doesn't have permission to edit the directory.</span></span> <span data-ttu-id="e100f-106">如果是，请使用 `sudo chmod o-w -R /usr/share/dotnet-tools` 命令删除访问权限。</span><span class="sxs-lookup"><span data-stu-id="e100f-106">If so, use the `sudo chmod o-w -R /usr/share/dotnet-tools` command to remove the access.</span></span>

### <a name="run-the-global-tool"></a><span data-ttu-id="e100f-107">运行全局工具</span><span class="sxs-lookup"><span data-stu-id="e100f-107">Run the global tool</span></span>

<span data-ttu-id="e100f-108">**选项 1** 对 sudo 使用完整路径：</span><span class="sxs-lookup"><span data-stu-id="e100f-108">**Option 1** Use the full path with sudo:</span></span>

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

<span data-ttu-id="e100f-109">**选项 2** 为每个工具添加一次工具的符号链接：</span><span class="sxs-lookup"><span data-stu-id="e100f-109">**Option 2** Add the symbol link of the tool, once per tool:</span></span>

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

<span data-ttu-id="e100f-110">然后使用以下命令运行：</span><span class="sxs-lookup"><span data-stu-id="e100f-110">And run with:</span></span>

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="e100f-111">卸载全局工具</span><span class="sxs-lookup"><span data-stu-id="e100f-111">Uninstall the global tool</span></span>

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="e100f-112">如果创建了符号链接，还需将其删除：</span><span class="sxs-lookup"><span data-stu-id="e100f-112">If you made a symbol link, you also need to remove it:</span></span>

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```
