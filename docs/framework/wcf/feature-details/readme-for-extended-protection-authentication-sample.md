---
title: 扩展保护身份验证示例自述文件
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: cc60ee32efcbe1e6ac1ce620fa1c17504db5197f
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690587"
---
# <a name="readme-for-extended-protection-authentication-sample"></a>扩展保护身份验证示例自述文件

扩展的保护是一种安全计划中拦截 (MITM) 攻击，在其中攻击者 （"人-中-干预"） 截获客户端的凭据，并使用它们来访问客户端的目标服务器上的安全资源。

有关详细信息，请参阅[扩展保护的身份验证概述](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md)。

> [!NOTE]
> 仅当承载于 IIS 上时，此示例才有效。 它不适用于 Visual Studio 开发服务器，原因是此服务器不支持 HTTPS。

## <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例

1. 安装 IIS 计算机上，从添加/删除程序-> Windows 功能。

2. 在 Windows 功能中打开 Windows 身份验证：Internet 信息服务-> 万维网服务-> 安全-> Windows 身份验证。

3. 在 Windows 功能中打开 HTTP 激活：Microsoft.NET Framework 3.5.1-> Windows Communication Foundation HTTP 激活。

4. 此示例要求客户端与服务器建立一个安全通道，因此它要求存在服务器证书，此证书可从 Internet 信息服务 (IIS) 管理器进行安装。

    1. 打开 IIS 管理器-> 服务器证书 （从功能视图选项卡）。

    2. 为了测试此示例，你可以创建一个自签名证书。 （如果不希望 Internet Explorer 提示证书不安全，可将证书安装到受信任的证书根颁发机构存储区中）。

5. 转至默认网站的“操作”窗格。 单击编辑站点-> 的绑定。 如果 HTTPS 不存在，则将其作为一种类型添加，端口号为 443，并分配在上一步中创建的 SSL 证书。

6. 生成服务。 这会在 IIS 中为你创建一个虚拟目录（从在项目属性中指定的生成后操作），并根据需要为要进行 Web 承载的服务复制 dll、.svc 和配置文件。

7. 打开 IIS 管理器。 右击在上一步中创建的虚拟目录 (ExtendedProtection)，然后选择“转换为应用程序”。

8. 在 IIS 管理器中为此虚拟目录打开“身份验证”模块，并启用“Windows 身份验证”。

9. 为此虚拟目录打开“Windows 身份验证”的“高级设置”，然后将其设置为“必选”，因为在此示例中，相应的 ExtendedProtection 设置已设置为“始终”。

10. 通过从浏览器窗口访问 URL 可测试此服务。 如果想要跨计算机访问此 URL，请确保为所有传入 HTTP 和 HTTPS 连接打开了防火墙。

11. 打开客户端配置文件，并提供有关完整的计算机名称\<客户端 >-\<终结点 >-address 属性替换\<full_machine_name >。

12. 运行客户端。 客户端通过建立安全通道并使用扩展保护与服务进行通信。
