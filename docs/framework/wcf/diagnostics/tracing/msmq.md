---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663721"
---
# <a name="msmq"></a>MSMQ
在 MSMQ 应用程序中，不会在 MSMQ 与队列通道之间传输任何额外活动。  
  
 另外，在执行 Send（发送）操作和 Receive（接收）操作时，还将 MSMQ 消息 ID 和 SOAP 消息 ID（连同活动 ID，如果存在）  
  
 作为队列通道跟踪的一部分来跟踪。  
  
 要求的传输接收操作的执行方式类似于其他任何传输 (接收字节-> 进程内消息-> 操作)。
