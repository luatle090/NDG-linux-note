# NDG-linux-note
								LINUX COMMAND LINE

 các command line để đọc tài liệu sử dụng lệnh man []: vd man ls
 các commnad line buil-in trong linux gõ --help: vd cd ==help

 Viết nhanh các command sử Tab để hoàn thiện câu lệnh

 Các lệnh trong command line ở option thì có thể viết riêng lẻ hoặc viết chung nhau
	ls -l -r : list ra long display và sắp xếp ngược
	ls -rl 	 : list ra long display và sắp xếp ngược
	ls -lr 	 : list ra long display và sắp xếp ngược

---------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------

## Lệnh ls: liệt kê các tập tin và thư mục
	ls -l: liệt kê theo dạng long display, đc sắp xếp theo A->Z
		total 32
		Vị trí các cột là 
		permissions | count | userOwner | groupOwner | size | timestamp | filename
		drwx------ 2 sysadmin sysadmin 4096 Dec 20  2017 Desktop                        
		drwx------ 4 sysadmin sysadmin 4096 Dec 20  2017 Documents


	ls -l -h: liệt kê theo dạng long display nhưng dung lượng thể hiện dễ đọc hơn
		total 32
		drwx------ 2 sysadmin sysadmin 4.0K Dec 20  2017 Desktop                        
		drwx------ 4 sysadmin sysadmin 4.0K Dec 20  2017 Documents

	ls -r: Sắp xếp ngược. Có thể kết hợp với các kiểu sắp xếp khác
		Videos  Templates  Public  Pictures  Music  Downloads  Documents  Desktop

	ls -t: sắp xếp theo timestamp theo thứ tự từ ngày mới -> ngày cũ

	ls -S: sắp xếp theo size theo thứ tự lớn -> bé

	ls -lSr: sắp xếp theo size nhưng theo tứ tự từ bé tới lớn

	ls Documents/School: Đứng tại thư mục hiện hành nhưng vẫn list ra được thư mục hoặc tập tin bên trong
		Art  Engineering Math

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## Các lệnh Di chuyển thư mục và in thư mục hiện hành

Lệnh pwd: Printing Working Directory, in ra thư mục hệ thống 
	pwd: in ra đường dẫn hiện đang đứng
	/home/sysadmin
	
Lệnh cd: Changing Directories, thay đổi vị trí thư mục
	cd ~: di chuyển tới $HOME

	cd /: Di chuyển tới root

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## Lệnh về super user:
	* su: cho phép hành động như 1 user khác, được thực hiện bằng cách tạo mới shell
	Shell chỉ đơn giản là input console cho phép bạn nhập lệnh command. Mặc định, nếu user
	account ko được chỉ định, thì su command sẽ mở shell của root user, cung cấp quyền hạn administrative

		su OPTIONS USERNAME 

	Đăng nhập vào su
		su -
		su -l
		su --login 

	Đăng xuất khỏi su
		exit

	* Lệnh về sudo: cho phép user thực thi command như là 1 user khác mà ko tạo mới shell.
	Thay vì thực thi command với quyền administrative, sử dụng sudo. Giống như su, 
	mặc định sẽ là root user

		sudo -u USERNAME: chuyển sang user khác mà ko phải là root

	sudo ls: Khi lệnh này hoàn tất, thì bạn vẫn đăng nhập ở quyền hạn user thay vì là su.
			 lệnh sudo chỉ cung cấp quyền hạn để thực thi command
			 Lệnh được thực hiện dưới dạng root nếu được đặt trước bằng lệnh sudo. Nếu không, lệnh được thực thi như một người dùng thông thường. 
