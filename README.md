# SMWrap-V3.4
<br><h3>www.smwrap.ru</h3>
<pre>
   1) Install smwrap3.4.0.6.exe 
   2) Cache' Intersystems необходимо выключить БД "CACHELIB" из режима только чтения. 
   3) Инсталляция do $system.OBJ.Load("c:\XML\SMWrap.xml","c") 
   4) Cache' Intersystems необходимо выключить БД "CACHELIB" в режима только чтения. 
   5) Запустить сервер: do RUN^%ZMRPMD()               
</pre>

 <h3> Скрипт для инсталляции:</h3>
 <pre>
      s OldNs=$zu(5)
      d $zu(5,"%SYS")
      set db=##class(SYS.Database).%OpenId("CACHELIB")
      set db.ReadOnly=0 
      w db.%Save()
      do $system.OBJ.Load("c:\XML\SMWrap.xml","c")    ; "c:\XML\SMWrap.xml" - путь к файлу на сервере   
      set db.ReadOnly=1
      w db.%Save()
      do $zu(5,OldNs)
      do RUN^%ZMRPMD()
 </pre>
  
   

