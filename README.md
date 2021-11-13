1-4 Выполнено

5. Ознакомьтесь с графическим интерфейсом VirtualBox, посмотрите как выглядит виртуальная машина, которую создал для вас Vagrant, 
   какие аппаратные ресурсы ей выделены. Какие ресурсы выделены по-умолчанию?
   
   Оперативная память: 1024 Мб
   Процессоры: 2
   HDD: 64 Гб
   Видеопамять: 4 Мб
   
6. Ознакомьтесь с возможностями конфигурации VirtualBox через Vagrantfile: документация. 
   Как добавить оперативной памяти или ресурсов процессора виртуальной машине?
   
   Чтобы изменить размер оперативной памяти и/или добавить ресурсов процессору надо в файле Vagrantfile раскомментировать 
    и изменить строки:
   
	   config.vm.provider "virtualbox" do |v|
		  v.memory = 1024
		  v.cpus = 2
	   end

7. vagrant ssh

8. 1. Какой переменной можно задать длину журнала history, и на какой строчке manual это описывается?
		HISTFILESIZE on line 817
		HISTSIZE on line 833
		
   2. Что делает директива ignoreboth в bash?
		HISTCONTROL - список значений, разделенных двоеточиями, управляющий тем, как команды сохраняются в списке истории. 
		Если список значений включает в себя ignorespace, то строки, начинающиеся с пробела, не сохраняются в списке истории. 
		Значение ignoredups приводит к тому, что строки, соответствующие предыдущей записи истории, не будут сохранены. 
		Значение ignoreboth является сокращением для ignorespace и ignoredups.
		
9. В каких сценариях использования применимы скобки {} и на какой строчке man bash это описано?
	
		Для ссылки на массивы и переменные массивов, извлечение значений из массивов служит синтаксическая форма $ { ... }
			on line 228
		function имя () { тело функции }
			on line 371
		{000..100} — пробежится по всем числам от 0 до 100
		{A..Z} — пробежится по всем буквам английского алфавита от A до Z

10. С учётом ответа на предыдущий вопрос, как создать однократным вызовом touch 100000 файлов? 

		touch new-file-{1..100000}.txt
		
		Это создаст файл new-file-1.txt, new-file-2.txt до new-file-100000.txt.
		
    Получится ли аналогичным образом создать 300000? Если нет, то почему?
	
		Нет. Будет ошибка - Argument list too long. 
		ARG_MAX - это максимальная длина длина аргументов командной строки
		
11. В man bash поищите по /\[\[. Что делает конструкция [[ -d /tmp ]]

		Возвращает статус 0 или 1 в зависимости от оценки условного выражения между скопками.
		Данное условное выражение проверяет наличие каталога /tmp
		
12. Основываясь на знаниях о просмотре текущих (например, PATH) и установке новых переменных; командах, которые мы рассматривали, добейтесь в выводе type -a bash в виртуальной машине наличия первым пунктом в списке:
    	bash is /tmp/new_path_directory/bash
	bash is /usr/local/bin/bash
	bash is /bin/bash
	
	Команды:
	
	mkdir /tmp/new_path_dir/
	cp /bin/bash /tmp/new_path_dir/
	PATH=/tmp/new_path_dir/:$PATH
	
13. Чем отличается планирование команд с помощью batch и at?

	Команда at используется для назначения одноразового задания на заданное время, 
	а команда batch — для назначения одноразовых задач, которые должны выполняться, 
	когда загрузка системы становится меньше 1.5.
	
14. Выйти из терминала Ubuntu с помощью команды exit
    Далее: 
	vagrant suspend
    
