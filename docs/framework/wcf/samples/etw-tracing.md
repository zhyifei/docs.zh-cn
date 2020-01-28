---
title: ETW 추적
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: a62403e61e0566d5e7b753ff951bf4b316209b6f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742112"
---
# <a name="etw-tracing"></a>ETW 추적
이 샘플에서는 ETW(Windows용 이벤트 추적) 및 이 샘플과 함께 제공된 `ETWTraceListener`를 사용하여 E2E(엔드투엔드) 추적을 구현하는 방법을 보여 줍니다. 该示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，并包括 ETW 跟踪。  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 本示例假定您熟悉[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)。  
  
 <xref:System.Diagnostics> 추적 모델의 추적 소스마다 데이터가 추적되는 위치와 방법을 결정하는 추적 수신기가 여러 개씩 있을 수 있습니다. 수신기의 형식에 따라 추적 데이터가 기록되는 형식이 정의됩니다. 다음 코드 샘플에서는 수신기를 구성에 추가하는 방법을 보여 줍니다.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 이 수신기를 사용하기 전에 ETW 추적 세션이 시작되어야 합니다. 이 세션은 Logman.exe 또는 Tracelog.exe를 사용하여 시작할 수 있습니다. SetupETW.bat 파일이 이 샘플에 포함되어 있으므로 ETW 추적 세션을 닫고 로그 파일을 완료하는 CleanupETW.bat 파일과 함께 세션을 설정할 수 있습니다.  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다. 有关这些工具的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=56580>  
  
 ETWTraceListener를 사용할 경우 추적은 이진 .etl 파일에 기록됩니다. ServiceModel 추적이 설정된 상태에서 생성된 모든 추적은 동일한 파일에 표시됩니다. 使用[服务跟踪查看器工具（svctraceviewer.exe）](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)来查看 .etl 和 .svclog 日志文件。 이 뷰어는 해당 소스에서 해당 대상 및 소비 지점까지 메시지를 추적하는 데 사용할 수 있는 시스템의 엔드투엔드 보기를 만듭니다.  
  
 ETW 추적 수신기는 순환 로깅을 지원합니다. 若要启用此功能，请参阅**开始**，**运行**，然后键入 `cmd` 以启动命令控制台。 다음 명령에서 `<logfilename>` 매개 변수를 로그 파일의 이름으로 바꿉니다.  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 `-f` 및 `-max` 스위치는 선택 사항입니다. 이러한 스위치는 각각 이진 순환 형식과 1000MB의 최대 로그 크기를 지정합니다. `-p` 스위치는 추적 공급자를 지정하는 데 사용됩니다. 위 예제에서 `"{411a0819-c24b-428c-83e2-26b41091702e}"`는 "XML ETW 샘플 공급자"의 GUID입니다.  
  
 세션을 시작하려면 다음 명령을 입력합니다.  
  
```console  
logman start Wcf  
```  
  
 로깅을 완료한 후 다음 명령을 사용하여 세션을 중지할 수 있습니다.  
  
```console  
logman stop Wcf  
```  
  
 此过程将生成二进制循环日志，可以通过所选的工具[（包括服务跟踪查看器工具（svctraceviewer.exe）](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)或 Tracerpt）进行处理。  
  
 若要详细了解如何执行循环日志记录，还可以查看[循环跟踪](../../../../docs/framework/wcf/samples/circular-tracing.md)示例。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 请确保已[为 Windows Communication Foundation 示例执行了一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成解决方案，请按照[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
    > [!NOTE]
    > RegisterProvider.bat, SetupETW.bat 및 CleanupETW.bat 명령을 사용하려면 로컬 관리자 계정으로 실행해야 합니다. 如果你使用的是 Windows Vista 或更高版本，则还必须使用提升的权限运行命令提示符。 为此，请右键单击 "命令提示符" 图标，然后单击 "以**管理员身份运行**"。  
  
3. 샘플을 실행하기 전에 RegisterProvider.bat를 클라이언트와 서버에서 실행합니다. 이렇게 하면 Service Trace Viewer에서 읽을 수 있는 추적을 생성하도록 결과 ETWTracingSampleLog.etl 파일이 설정됩니다. 이 파일은 C:\logs 폴더에 있습니다. 이 폴더가 없을 경우 만들어야 하며 그렇지 않으면 추적이 생성되지 않습니다. 그런 다음 클라이언트 및 서버 컴퓨터에서 SetupETW.bat를 실행하여 ETW 추적 세션을 시작합니다. SetupETW.bat 파일은 CS\Client 폴더에 있습니다.  
  
4. 若要以单机配置或跨计算机配置来运行示例，请按照[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)中的说明进行操作。  
  
5. 샘플이 완료되면 CleanupETW.bat를 실행하여 ETWTracingSampleLog.etl 파일 만들기를 완료합니다.  
  
6. Service Trace Viewer 내에서 ETWTracingSampleLog.etl 파일을 엽니다. 이진 형식 파일을 .svclog 파일로 저장하라는 메시지가 표시됩니다.  
  
7. 서비스 추적 뷰어 내에서 새로 만든 .svclog 파일을 열어 ETW 및 ServiceModel 추적을 봅니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> 如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 이 샘플은 다음 디렉터리에 있습니다.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a>另请参阅

- [AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
