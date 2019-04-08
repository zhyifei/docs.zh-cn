---
ms.openlocfilehash: 08c16f261338148619de2e484c73046b9d9a6bfe
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761268"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="0cf7b-101">.NET Framework 4.6 在注册表中注册自身时，不会使用 4.5.x.x 版本</span><span class="sxs-lookup"><span data-stu-id="0cf7b-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0cf7b-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="0cf7b-102">Details</span></span>|<span data-ttu-id="0cf7b-103">正如所料，在注册表（位于 <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>）中为 .NET Framework 4.6 设置的版本密钥以“4.6”开头，而不是“4.5”。</span><span class="sxs-lookup"><span data-stu-id="0cf7b-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="0cf7b-104">对于根据这些注册表项了解计算机上应安装哪些版本的 .NET Framework 的应用，应将其更新，以了解 4.6 是新的可行版本，与之前的 4.5.x 版本兼容。</span><span class="sxs-lookup"><span data-stu-id="0cf7b-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="0cf7b-105">建议</span><span class="sxs-lookup"><span data-stu-id="0cf7b-105">Suggestion</span></span>|<span data-ttu-id="0cf7b-106">通过查找 4.5 注册表项来更新探测 .NET Framework 4.5 安装的应用，从而也可以接受 4.6。</span><span class="sxs-lookup"><span data-stu-id="0cf7b-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="0cf7b-107">范围</span><span class="sxs-lookup"><span data-stu-id="0cf7b-107">Scope</span></span>|<span data-ttu-id="0cf7b-108">边缘</span><span class="sxs-lookup"><span data-stu-id="0cf7b-108">Edge</span></span>|
|<span data-ttu-id="0cf7b-109">版本</span><span class="sxs-lookup"><span data-stu-id="0cf7b-109">Version</span></span>|<span data-ttu-id="0cf7b-110">4.6</span><span class="sxs-lookup"><span data-stu-id="0cf7b-110">4.6</span></span>|
|<span data-ttu-id="0cf7b-111">类型</span><span class="sxs-lookup"><span data-stu-id="0cf7b-111">Type</span></span>|<span data-ttu-id="0cf7b-112">运行时</span><span class="sxs-lookup"><span data-stu-id="0cf7b-112">Runtime</span></span>|

