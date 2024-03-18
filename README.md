ClickOnce has prerequisite for
“Sql server 2012 Express localDb”
“Sql server 2016 Express localDb”
“Sql server 2017 Express localDb”
“Sql server 2012 Express localDb”
but not for
“Sql server 2022 Express localDb”.
https://developercommunity.visualstudio.com/t/ClickOnce-Sql-server-2022-Express-local/10614924

- copy the files into c:\Program Files (x86)\Microsoft SDKs\ClickOnce Bootstrapper\Packages
	- you need admin rights
- now the new dependency should appear in VS
	- you do not have to restart VS, just press in "project / publish" the "more actions / edit"
- creating from scratch
	- start from "c:\Program Files (x86)\Microsoft SDKs\ClickOnce Bootstrapper\Packages\SqlLocalDB2019"
	- modify product.xml: ProductCode, SearchPath
		- <BypassIf Property="sqllocaldbVersion" Compare="VersionGreaterThanOrEqualTo" Value="2022.1.1.1"/>
		- I did not change: vc_redist.x64.exe
	- modify en / eula.rtf, 2019 -> 2022
	- modify en / package.xml, 2019 -> 2022
		- it is not easy to figure out the direct download link (sqllocaldb_64)
		- https://blog.dotsmart.net/2022/11/24/sql-server-2022-localdb-download/
