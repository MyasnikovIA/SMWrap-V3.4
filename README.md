# SMWrap-V3.4 среда компонентной разработки программ (Cache Intersystems)
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
      set db=##class(SYS.Database).%OpenId("CACHELIB") // from Cache'
      // set db=##class(SYS.Database).%OpenId("IRISLIB") // from Iris'
      set db.ReadOnly=0 
      w db.%Save()
      do $system.OBJ.Load("c:\XML\SMWrap.xml","c")    ; "c:\XML\SMWrap.xml" - путь к файлу на сервере   
      set db.ReadOnly=1
      w db.%Save()
      do $zu(5,OldNs)
      do RUN^%ZMRPMD
 </pre>


<br>
SMWrap - среда быстрой разработки приложений (Rapid Application Development) для создания высокоэффективных Intranet/Internet приложений, которые используют СУБД Cache 2015 или 2016 . Приложения SMWrap - это полноценные GUI приложения, которые строятся на архитектуре тонкого клиента. Для соединения с базой данных используется протокол TCP/IP. Весь код приложения (включая интерфейс) содержится в классах Cache внутри БД, поэтому на стороне клиента необходимо иметь только выполняемый файл размером  2,4 Мб. Данный файл может быть загружен с сайта. После чего мастер установки установит SMWrap на Ваш компьютер. Для установки и использования SMWrap Ваши клиенты должны знать только IP адрес компьютера, на котором установлен сервер Cache и имя приложения. Весь код приложения и интерфейса хранится внутри БД, поэтому при использовании SMWrap стоимость сопровождения резко уменьшается. Например, для изменения какой-либо формы Вашего приложения достаточно загрузить класс Cache и откомпилировать его. 
Технология SMWrap - это технология действительно тонкого клиента: SMWrap со стороны клиента - это "браузер", который понимает команды специального формата и создает и управляет соответствующими GUI приложениями. Он не знает ничего о приложении, которое выполняет, а все что он делает - это выполнение входящих команд и уведомление сервера о событиях, которые произошли как результат действий клиента.
<br><br>

Приложение SMWrap состоит из классов Cache. Язык, который используется для разработки приложений SMWrap - тот же самый язык, который используется СУБД Cache. Для версий 2015 или 2016 - это Cache ObjectScript, а в будущем могут использоваться Cache Basic или другие языки, поддерживаемые данной СУБД
<br><br>

SMWrap - это инструментарий, необходимый для быстрой разработки приложений. Перечень этих свойств позволяет программистам уменьшить период разработки приложения: 
<br>•	"Explorer-подобный" интерфейс для быстрого редактирования классов 
<br>•	Профессиональный дизайнер форм
<br>•	Мощный генератор отчетов
<br>•	Широкий выбор компонентов для построения изысканных GUI приложений 
<br>•	Профессиональный редактор кода с подсветкой синтаксиса 
<br>•	CodeInsight (использует предопределенные шаблоны для ускорения программирования) 
<br>•	CodeComplete (показывает список доступных свойств и методов объекта для объектных свойств) 
<br>Набор мастеров для быстрой и легкой разработки 
<br><br>
 
Часто приложения, работающие с БД, должны печатать отчеты. SMWrap содержит встроенный генератор отчетов, который позволяет создавать профессиональные отчеты при минимальном написании кода: 
<br>
<br>•	Встроенный профессиональный редактор отчетов 
<br>•	Профессиональный, настраиваемый превьюер 
<br>•	Быстрая подготовка и печать 
<br>•	Неограниченное количество страниц в отчете 
<br>•	Широкий диапазон типов отчетов 
<br>•	Широкий диапазон форматов бумаги 
<br>•	Богатая библиотека компонентов 
<br>•	Экспорт отчетов в форматах HTML, RTF, TXT и CSV 
<br>•	Поиск данных в подготовленном отчете 
<br>Встроенный интерпретатор для контроля и управления процессом построения отчета.
<br><br>
 
Профессиональная головная боль разработчиков - внедрение приложений. Приложения "клиент-сервер" часто требуют сложной процедуры внедрения. Обновление и поддержка подобных приложений часто требует многих ресурсов и значительных затрат. SMWrap так же часто лишает необходимости в установке клиентской части ПО: любой пользователь может загрузить клиент SMWrap с сайта и он (или она) должны только ввести параметры соединения к серверу БД и имя приложения. Установка новой версии клиента SMWrap так же выполняется одним запуском. Установка серверной части приложения так же очень проста. В SMWrap имеется мастер импорта и экспорта, который автоматизирует процесс установки приложения. Обновление приложения так же осуществляется данным мастером или инструментами Cache (Terminal, Object Architect, Проводник). 
<br><br>
 
Для обеспечения процедуры авторизации пользователя приложения в SMWrap имеются встроенные средства авторизации. Разработчики могут реализовать более сложные средства путем замены стандартных алгоритмов SMWrap.
