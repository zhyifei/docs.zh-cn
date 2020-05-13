---
title: 网络中断性变更
description: 列出 .NET Core 中网络的中断性变更。
ms.date: 05/05/2020
ms.openlocfilehash: 07e0b2e062ce244cd6312bbe08bcc63db4c74347
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859615"
---
# <a name="networking-breaking-changes"></a>网络中断性变更

本页记录了以下中断性变更：

| 重大更改 | 引入的版本 |
| - | - |
| [HttpRequestMessage.Version 的默认值已更改为 1.1](#default-value-of-httprequestmessageversion-changed-to-11) | 3.0 |
| [WebClient.CancelAsync 并不总是立即取消](#webclientcancelasync-doesnt-always-cancel-immediately) | 2.0 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
