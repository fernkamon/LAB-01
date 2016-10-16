# ใบงานที่ 1 เรื่อง การเขียนโปรแกรม Win32 ด้วยภาษา C
##วัตถุประสงค์

1. เพื่อให้นักศึกษาสามารถบอกวิธีการเขียนโปรแกรมบน Windows ด้วยฟังก์ชัน Win32 API ได้
2. เพื่อให้นักศึกษาสามารถใช้เครื่องมือต่างๆ ในการสร้าง Application บน IDE ได้

##ลำดับการทดลอง

1. เรียกโปรแกรม Microsoft Visual Studio 
2. สร้าง Project ใหม่  โดยเลือกเมนู File >> New >> Project… (Ctrl+Shift+N) จะปรากฏหน้าต่าง New Project ดังรูปที่ 1 ให้ทำตามขั้นตอน 2.1 – 2.4
![](https://github.com/Desktop-Programming-Lab-2559/LAB-01/blob/master/imgs/pic1.png)
    2.1 ช่อง Templates: ให้เลือก Visual C++ และเลือกชนิด project เป็น Empty Project

    2.2 ช่อง Name: ให้ใส่ชื่อของ Project เป็น EasyWin32

    2.3 ช่อง Location: ให้เลือกตำแหน่งที่จะสร้าง Project

    2.4 ส่วนที่เหลือ ให้คงไว้ตามที่ปรากฏ กด OK 

3 เพิ่ม source code ให้กับ project โดยการเลือกเมนู PROJECT >> Add New Item…
   
    3.1 ตั้งชื่อไฟล์เป็น EasyMain.cpp
    3.2 กด Add เพื่อเพิ่มไฟล์


4 พิมพ์โปรแกรมดังต่อไปนี้ลงในไฟล์ EasyMain.cpp
 
```c 
#include <windows.h>

int WINAPI
WinMain(HINSTANCE hInst, HINSTANCE hPrev, LPSTR  lpCmdLine, int nCmdshow)
{
    MessageBox(NULL, "Hello World! This is my first win32 program!",
	"Lesson1", MB_OK);
    return 0;
}
```

**หมายเหตุ**
ใน Windows นั้น ฟังก์ชันแรกในโปรแกรมของเราที่จะถูกเรียกใช้คือ WinMain ต่างจากในภาษา C ที่ใช้ main()<br>
อ่านเพิ่มเติม 
* [WinMain entry point](https://msdn.microsoft.com/en-us/library/windows/desktop/ms633559(v=vs.85).aspx)
* [MessageBox](https://msdn.microsoft.com/en-us/library/windows/desktop/ms645505(v=vs.85).aspx)
* [HINSTANCE](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383751(v=vs.85).aspx)

5 กดปุ่ม Ctrl+F5 เพื่อดูผลการทำงานของโปรแกรม

## บันทึกผลการทดลอง
	จากผลการทดลอง พบว่า เมื่อพิมพ์ Code ตามที่กำหนดแล้ว เมื่อทำการรันผล จะปรากฎBlock ขึ้นมาดังรูป
![](https://github.com/fernkamon/LAB-01/blob/master/imgs/MB_OK.PNG)


## คำถาม 
1. นักศึกษาพบปัญหาในการคอมไพล์โปรแกรมหรือไม่ ถ้าเจอให้บอกที่ผิดและแนวทางการแก้ไข

	<code> -ไม่มีปัญหาอะไรค่ะ สามารถคอมไพล์หาค่าได้ปกติ </code>
	
2. ให้ทดลองแก้ไข <code> MessageBox(...) </code> โดยการเปลี่ยน <code> MB_OK </code> เป็นค่าอื่นๆ [ดูได้จากอ้างอิงตามลิงค์นี้](https://github.com/Desktop-Programming-Lab-2559/LAB-01/blob/master/message-box.md)
	
	<code> ยกตัวอย่างเช่น  </code>   
	<code>-เปลี่ยนให้เป็น MB_ICONFORMATION </code>
	
![](https://github.com/fernkamon/LAB-01/blob/master/imgs/MB_ICONERROR.PNG)

	-เปลี่ยนให้เป็น MB_ICONFORMATION
	
![](https://github.com/fernkamon/LAB-01/blob/master/imgs/MB_ICONFORMATION.PNG)

	-เปลี่ยนให้เป็น MB_ICONQUEATION
	
![](https://github.com/fernkamon/LAB-01/blob/master/imgs/MB_ICONQUEATION.PNG)
				
	-เปลี่ยนให้เป็น MB_ICONWARINING
	
![](https://github.com/fernkamon/LAB-01/blob/master/imgs/MB_ICONWARNING.PNG)

	หรือเปลี่ยนให้สามารถใช้ได้ทั้งICONและปุ่มในการกดแบบต่างๆ เช่น
	-MB_ICONWRAINING | MB_RETRYCANCEL
	
![](https://github.com/fernkamon/LAB-01/blob/master/imgs/CaptureWraining.PNG)

	-MB_ICONERROR | MB_OKCANCEL

![](https://github.com/fernkamon/LAB-01/blob/master/imgs/MIXicon%20errorokcancle.PNG)

##[อ้างอิง](https://github.com/Desktop-Programming-Lab-2559/LAB-01/wiki/References)
WinMain (..), MessageBox(..) 
 
* [theForger's Win32 API Programming Tutorial](http://www.winprog.org/tutorial/start.html)
* [Win32 programming tutorials](http://www.win32developer.com/tutorial.shtm)

* [Building a Win32 App, Part 2: Windows and Messages](https://www.codementor.io/c_plus_plus/tutorial/build-win32-api-app-windows-messages-c-cpp-visual-studio)
