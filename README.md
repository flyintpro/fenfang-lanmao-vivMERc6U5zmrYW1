
如题，有客户咨询这个问题：Exadata X6支持的最新image和19c数据库版本？
直观感觉，看到X6这个型号就觉得是很老的机器了，毕竟现在最新都X10M了。


首先，去查MOS文档：


* Exadata Database Machine and Exadata Storage Server Supported Versions (Doc ID 888828\.1\)


在`Exadata System Software Requirements for Exadata Database Machine Hardware`章节可以看到X6 支持的 image版本：


* Exadata 12\.1\.2\.3\.1 through 24\.1
这也就是说支持最新的image到了24\.1这个版本，而这个版本的image，连最新的Oracle 23ai数据库都能装！



> 23ai Long Term Release \=\> Supported: Exadata 24\.1 or higher
> Database 23ai requires storage server and database server Exadata version to be 24\.1 or higher, and fabric switch version to be that which is supplied with Exadata 24\.1 or higher. Full Exadata offload functionality for all Database 23ai features is available starting in Exadata 24\.1\.


客户没有23ai需求，只关注19c的情况，而19c需要的image版本，只要在19\.1\.2或以上就OK，推荐23或24版本。



> 19c Long Term Release (Recommended) \=\> Supported: Exadata 19\.1\.2\.0\.0 or higher
> Exadata 24\.1 requires ACFS Patch 36114443 in Grid Infrastructure 19c home, which is included in 19\.23\.
> Database 19c requires storage server and database server Exadata version to be 19\.1\.2\.0\.0 or higher, and InfiniBand switch version to be 2\.2\.11\-2 or higher (that which is supplied with Exadata 19\.1\.2\.0\.0\). It is not supported to use lower versions on storage servers, database servers, or InfiniBand switches.


而数据库19c具体最新的版本，是取决于当前19c最新的RU的，目前还是19\.25，是去年10月份发布的，按照惯例，预计这个月会推出更新的19\.26：


![](https://img2023.cnblogs.com/blog/635610/202501/635610-20250102151531484-1545213344.jpg)


参考MOS文档：


* Assistant: Download Reference for Oracle Database/GI Update, Revision, PSU, SPU(CPU), Bundle Patches, Patchsets and Base Releases (Doc ID 2118136\.2\)


总结下，X6支持的image版本：Exadata 12\.1\.2\.3\.1 through 24\.1，安装新版本的image，不但能支持19c数据库最新的RU版本，还支持最新的23ai数据库。
如果你还想知道其他Exadata型号的image版本和数据库版本支持情况，都可以结合查询MOS文档888828\.1、2118136\.2获取到官方说明。


 本博客参考[西部世界官网](https://www.xbsj9.com)。转载请注明出处！
