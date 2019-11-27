---
title: FIPS 相容性-.NET Core
description: 介绍 .NET Core 美国联邦信息处理标准（FIPS）符合性。
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205076"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a>.NET Core 美国联邦信息处理标准（FIPS）符合性

美国联邦信息处理标准（FIPS）发布140-2 是美国政府标准，用于定义信息技术产品中加密模块的最低安全要求，如信息的第5131节中所定义技术管理改革行为1996。

.NET Core：

* 将加密基元调用传递到基础操作系统提供的标准模块。
* **不**强制在 .net Core 应用程序中使用 FIPS 批准的算法或密钥大小。

系统管理员负责为操作系统配置 FIPS 相容性。

如果为符合 FIPS 标准的环境编写代码，开发人员负责确保不会使用不合规的 FIPS 算法。

有关 FIPS 相容性的详细信息，请参阅以下文章：

* [Windows FIPS 相容性](/windows/security/threat-protection/fips-140-validation)
* [针对 FIPS 相容性配置 Windows](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [10.2. 联邦信息处理标准（FIPS）](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
