---
title: Database Access Activities
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: 2463c3a87be7f7e248572d45e018b72661f4f8c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62005214"
---
# <a name="database-access-activities"></a>Database Access Activities
데이터베이스 액세스 활동을 사용하여 워크플로 내에서 데이터베이스에 액세스할 수 있습니다. 이러한 활동을 검색 하거나 정보를 수정 하 고 사용 하 여 데이터베이스에 액세스 허용 [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) 데이터베이스에 액세스할 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
>  `<InstallDrive>:\WF_WCF_Samples`
>
>  이 디렉터리가 없으면 다운로드 페이지로 이동할 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플입니다. 이 샘플은 다음 디렉터리에 있습니다.
>
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a>데이터베이스 활동
 다음 단원에서는 이 샘플에 포함된 활동 목록에 대해 자세히 설명합니다.

## <a name="dbupdate"></a>DbUpdate
 데이터베이스의 내용을 수정(삽입, 업데이트, 삭제 등)하는 SQL 쿼리를 실행합니다.

 이 클래스는 <xref:System.Activities.AsyncCodeActivity>에서 파생되어 비동기 기능을 사용하므로 작업을 비동기적으로 수행합니다.

 공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.

 실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.

 `DbUpdate`가 실행된 후에는 영향을 받은 레코드의 수가 `AffectedRecords` 속성에서 반환됩니다.

```
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|인수|설명|
|-|-|
|ProviderName|ADO.NET 공급자 고정 이름입니다. 이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.|
|ConnectionString|데이터베이스에 연결할 연결 문자열입니다. 이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.|
|ConfigName|연결 정보가 저장된 구성 파일 섹션의 이름입니다. 이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.|
|CommandType|실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.|
|Sql|실행할 SQL 명령입니다.|
|매개 변수|SQL 쿼리의 매개 변수 컬렉션입니다.|
|AffectedRecords|마지막 작업의 영향을 받은 레코드 수입니다.|

## <a name="dbqueryscalar"></a>DbQueryScalar
 데이터베이스에서 단일 값을 검색하는 쿼리를 실행합니다.

 이 클래스는 <xref:System.Activities.AsyncCodeActivity%601>에서 파생되어 비동기 기능을 사용하므로 작업을 비동기적으로 수행합니다.

 공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.

 실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.

 후 `DbQueryScalar` 는 실행에서 스칼라가 반환 됩니다 합니다 `Result out` 인수 (형식의 `TResult`되는 기본 클래스에 정의 된 <xref:System.Activities.AsyncCodeActivity%601>).

```
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|인수|설명|
|-|-|
|ProviderName|ADO.NET 공급자 고정 이름입니다. 이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.|
|ConnectionString|데이터베이스에 연결할 연결 문자열입니다. 이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.|
|ConfigName|연결 정보가 저장된 구성 파일 섹션의 이름입니다. 이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.|
|CommandType|실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.|
|Sql|실행할 SQL 명령입니다.|
|매개 변수|SQL 쿼리의 매개 변수 컬렉션입니다.|
|결과|쿼리가 실행된 후에 얻은 스칼라입니다. 이 인수는 `TResult` 형식입니다.|

## <a name="dbquery"></a>DbQuery
 개체 목록을 검색하는 쿼리를 실행합니다. 같은 매핑 함수가 실행 되는 쿼리를 실행 한 후 (수 <xref:System.Func%601> < `DbDataReader`를 `TResult`> 요소나 <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>). 이 매핑 함수는 `DbDataReader`에서 레코드를 가져오고 이를 반환할 개체에 매핑합니다.

 공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.

 실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.

 SQL 쿼리의 결과는 `DbDataReader`를 사용하여 검색됩니다. 활동에서는 `DbDataReader`를 반복하고 `DbDataReader`의 행을 `TResult`의 인스턴스에 매핑합니다. 사용자 `DbQuery` 매핑 코드 및이 두 가지 방법으로 수행할 수 있습니다를 제공 해야 하는:를 사용 하는 <xref:System.Func%601> < `DbDataReader`, `TResult`> 또는 <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>. 첫 번째의 경우에는 단일 실행 펄스에서 매핑이 수행됩니다. 따라서 속도가 더 빠르지만 매핑이 XAML로 serialize될 수 없습니다. 두 번째의 경우에는 매핑이 여러 펄스에서 수행됩니다. 따라서 속도가 더 느릴 수 있지만, 매핑이 XAML로 serialize되고 선언적으로 작성될 수 있으며 기존 활동이 매핑에 참여할 수 있습니다.

```
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|인수|설명|
|-|-|
|ProviderName|ADO.NET 공급자 고정 이름입니다. 이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.|
|ConnectionString|데이터베이스에 연결할 연결 문자열입니다. 이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.|
|ConfigName|연결 정보가 저장된 구성 파일 섹션의 이름입니다. 이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.|
|CommandType|실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.|
|Sql|실행할 SQL 명령입니다.|
|매개 변수|SQL 쿼리의 매개 변수 컬렉션입니다.|
|Mapper|매핑 함수 (<xref:System.Func%601><`DbDataReader`, `TResult`>) 레코드를 사용 하는 합니다 `DataReader` 형식의 개체의 인스턴스를 반환 하는 쿼리 실행 결과로 얻은 `TResult` 를추가할수`Result` 컬렉션입니다.<br /><br /> 이 경우 매핑은 단일 실행 펄스에서 수행되지만 디자이너를 사용하여 선언적으로 작성될 수는 없습니다.|
|MapperFunc|매핑 함수 (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) 레코드를 사용 하는 합니다 `DataReader` 형식의 개체의 인스턴스를 반환 하는 쿼리 실행 결과로 얻은 `TResult` 를추가할수`Result` 컬렉션입니다.<br /><br /> 이 경우에는 여러 실행 펄스에서 매핑이 수행됩니다. 이 함수는 XAML로 serialize되고 선언적으로 작성될 수 있으며 기존 활동이 매핑에 참여할 수 있습니다.|
|결과|쿼리를 실행하고 `DataReader`의 각 레코드에 대해 매핑 함수를 실행한 결과로 얻은 개체 목록입니다.|

## <a name="dbquerydataset"></a>DbQueryDataSet
 <xref:System.Data.DataSet>을 반환하는 쿼리를 실행합니다. 이 클래스는 작업을 비동기적으로 수행합니다. 파생 되므로 <xref:System.Activities.AsyncCodeActivity> < `TResult`> 되어 비동기 기능을 사용 합니다.

 공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.

 실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.

 후는 `DbQueryDataSet` 실행 되는 `DataSet` 반환 됩니다는 `Result out` 인수 (형식의 `TResult`되는 기본 클래스에 정의 된 <xref:System.Activities.AsyncCodeActivity%601>).

```
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|인수|설명|
|-|-|
|ProviderName|ADO.NET 공급자 고정 이름입니다. 이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.|
|ConnectionString|데이터베이스에 연결할 연결 문자열입니다. 이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.|
|ConfigName|연결 정보가 저장된 구성 파일 섹션의 이름입니다. 이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.|
|CommandType|실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.|
|Sql|실행할 SQL 명령입니다.|
|매개 변수|SQL 쿼리의 매개 변수 컬렉션입니다.|
|결과|쿼리가 실행된 후에 얻은 <xref:System.Data.DataSet>입니다.|

## <a name="configuring-connection-information"></a>연결 정보 구성
 모든 DbActivity는 동일한 구성 매개 변수를 공유합니다. 다음과 같은 두 가지 방법으로 DbActivity를 구성할 수 있습니다.

-   `ConnectionString + InvariantName`: ADO.NET 공급자 고정 이름과 연결 문자열을 설정 합니다.

    ```
    Activity dbSelectCount = new DbQueryScalar<DateTime>()
    {
        ProviderName = "System.Data.SqlClient",
        ConnectionString = @"Data Source=.\SQLExpress;
                             Initial Catalog=DbActivitiesSample;
                             Integrated Security=True",
        Sql = "SELECT GetDate()"
    };
    ```

-   `ConfigName`: 연결 정보를 포함 하는 구성 섹션의 이름을 설정 합니다.

    ```xml
    <connectionStrings>
        <add name="DbActivitiesSample"
             providerName="System.Data.SqlClient"
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
      </connectionStrings>
    ```

-   활동에서는 다음과 같이 구성합니다.

    ```
    Activity dbSelectCount = new DbQueryScalar<int>()
    {
        ConfigName = "DbActivitiesSample",
        Sql = "SELECT COUNT(*) FROM Roles"
    };
    ```

## <a name="running-this-sample"></a>샘플 실행

### <a name="setup-instructions"></a>설치 지침
 이 샘플에서는 데이터베이스를 사용합니다. 샘플과 함께 설치 및 로드 스크립트(Setup.cmd)가 제공되며, 이 파일은 명령 프롬프트를 사용하여 실행해야 합니다.

 Setup.cmd 스크립트는 다음을 수행하는 SQL 명령이 포함된 CreateDb.sql 스크립트 파일을 호출합니다.

-   DbActivitiesSample이라는 데이터베이스를 만듭니다.

-   Roles 테이블을 만듭니다.

-   Employees 테이블을 만듭니다.

-   Roles 테이블에 3개의 레코드를 삽입합니다.

-   Employees 테이블에 12개의 레코드를 삽입합니다.

##### <a name="to-run-setupcmd"></a>Setup.cmd를 실행하려면

1. 명령 프롬프트를 엽니다.

2. DbActivities 샘플 폴더로 이동합니다.

3. "Setup.cmd"를 입력 하 고 ENTER 키를 누릅니다.

    > [!NOTE]
    >  Setup.cmd에서는 로컬 컴퓨터의 SqlExpress 인스턴스에 샘플을 설치합니다. 다른 SQL 서버 인스턴스에 샘플을 설치하려면 Setup.cmd를 새 인스턴스 이름으로 편집하세요.

##### <a name="to-uninstall-the-sample-database"></a>샘플 데이터베이스를 제거하려면

1. 명령 프롬프트에서 샘플 폴더로 이동하여 Cleanup.cmd를 실행합니다.

##### <a name="to-run-the-sample"></a>이 샘플을 실행하려면

1. Visual Studio 2010에서 솔루션을 열으십시오

2. Ctrl+Shift+B를 눌러 솔루션을 컴파일합니다.

3. Ctrl+F5를 눌러 샘플을 디버깅하지 않고 실행합니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
