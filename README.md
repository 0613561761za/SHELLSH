# SHELLSH
เข้ารหัสไฟล์ ป้องกันนิดหน่อย


sudo apt-get install libc6-dev

https://codeload.github.com/Utappia/shellscript-to-binary-converter/zip/master


cd where-the-extracted-is
make 
sudo make install


sudo apt install shc






==================================================================================

ใช้คำสั่งต่อไปนี้เพื่อสร้างไฟล์ไบนารีของscript.sh
shc -T -f script.sh
ตัวเลือก

ตัวเลือกบรรทัดคำสั่งที่ใช้ได้ก็คือ:
==================================================================================

# -eวันที่: วันหมดอายุในรูปแบบ dd / mm / yyyy [ค่าเริ่มต้น: ไม่มี]

# -m message: ข้อความที่จะแสดงเมื่อหมดอายุ [default: "กรุณาติดต่อผู้ให้บริการของคุณ"]

# -f script_name: ชื่อไฟล์ของสคริปต์ที่จะคอมไพล์

# -i inline_option: ตัวเลือกอินไลน์สำหรับเชลล์ล่ามคือ: -e

# -x comand: exec คำสั่งเป็นรูปแบบ printf เช่น: exec ('% s', @ ARGV);

# -l last_option: ตัวเลือกสุดท้ายของเชลล์คือ: -

# -rผ่อนคลายความปลอดภัย สร้างไบนารีแบบ redistributable ซึ่งทำงานบนระบบต่างๆที่ใช้ระบบปฏิบัติการเดียวกัน

# -Vการรวบรวมข้อมูล verbose -D เปิดใช้งานการเรียกค้นดีบักเกอร์

# -Tอนุญาตให้ไบนารีสามารถตรวจสอบได้ (ใช้ strace, ptrace, truss ฯลฯ )

# -Cแสดงใบอนุญาตและออก

# -Aแสดงนามธรรมและออก

# -hแสดงความช่วยเหลือและออก

==================================================================================

# ผลลัพธ์และการสนทนา
SHC ตัวเองไม่ใช่คอมไพเลอร์เช่น cc แต่จะเข้ารหัสและเข้ารหัสลับของเชลล์สคริปต์และสร้างซอร์สโค้ด C พร้อมด้วยความสามารถในการหมดอายุเพิ่มเติม จากนั้นจะใช้คอมไพเลอร์ระบบเพื่อคอมไพล์ไบนารีที่ถูกถอดออกซึ่งทำงานเหมือนกับสคริปต์ต้นฉบับ เมื่อดำเนินการไบนารีที่คอมไพล์จะถอดรหัสและรันโค้ดด้วยตัวเลือก shell -c Unfortunatelly ก็จะไม่ให้คุณปรับปรุงความเร็วใด ๆ เป็นโปรแกรม C จริงจะ

ไบนารีที่คอมไพล์จะยังคงขึ้นอยู่กับเชลล์ที่ระบุไว้ในบรรทัดแรกของโค้ดเชลล์ (เช่น #! / bin / sh) ดังนั้น shc จะไม่สร้างไบนารีที่เป็นอิสระอย่างสมบูรณ์

==================================================================================

# วัตถุประสงค์หลักของ SHC คือการปกป้องสคริปต์ของคุณจากการดัดแปลงแก้ไขหรือการตรวจสอบ หากต้องการแจกจ่ายสคริปต์ แต่ไม่ต้องการให้ผู้อื่นสามารถอ่านได้
