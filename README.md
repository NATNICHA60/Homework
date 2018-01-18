"Homework" 

เริ่มต้นใช้งาน Git Repository
คุณสามารถสร้างโปรเจคใน Git โดยใช้สองวิธีหลัก วิธีแรกคือการนำเข้าโปรเจคหรือแฟ้มข้อมูลที่มีอยู่แล้วเข้าไปใน Git ส่วนวิธีที่สองคือการ clone จาก repository ที่อยู่ในเซิร์ฟเวอร์อื่น

- การสร้าง Repository จากแฟ้มข้อมูลที่มีอยู่แล้ว  สำหรับวิธีนี้ ให้ไปที่แฟ้มข้อมูลที่คุณต้องการเริ่มใช้งาน Git และพิมพ์คำสั่ง     $ git init
คำสั่งนี้จะสร้างแฟ้มข้อมูลย่อยชื่อ .git ซึ่งเก็บแฟ้มโครงสร้างของ Git repository เปล่า ๆ ที่ยังไม่มีเนื้อหาใด ในขั้นตอนนี้แฟ้มที่อยู่ในโปรเจคของคุณจะยังไม่ถูก track โดย Git 
เพื่อที่จะเริ่มเก็บประวัติการแก้ไขของแฟ้มที่มีอยู่ คุณจะต้องเพิ่มแฟ้มเข้าไปใน repository เสียก่อน โดยใช้คำสั่ง git add กับแฟ้มที่คุณต้องการเก็บประวัติ ตามด้วยการ commit:
			$ git add *.c
			$ git add README
			$ git commit –m 'เริ่มเก็บประวัติ'
			
		หลังจาก commit คุณก็จะได้ repository ที่เริ่มเก็บประวัติของแฟ้มต่าง ๆ ในโปรเจคของคุณแล้ว
		
- การ clone จาก repository ที่มีอยู่แล้ว
		ถ้าคุณต้องการคัดลอก repository ที่มีอยู่แล้ว 
		- ยกตัวอย่างเช่น จากโปรเจคที่คุณอยากมีส่วนร่วม
		- คำสั่งที่คุณต้องใช้คือ git clone ถ้าคุณเคยใช้ระบบ VCS อื่นอย่าง Subversion คุณจะสังเกตเห็นว่าคำสั่งคือ clone ไม่ใช่ checkout ซึ่งความแตกต่างนี้เป็นความแตกต่างที่สำคัญมาก 
		   เพราะมันหมายความว่า Git ทำการคัดลอกข้อมูลเกือบทุกอย่างที่อยู่ในเซิร์ฟเวอร์ ทุกเวอร์ชั่นของทุกแฟ้มมีมีในประวัติของโปรเจคจะถูกคัดลอกมายังเครื่องของคุณเมื่อคุณใช้คำสั่ง git clone 
		 ในความเป็นจริงถ้าเกิดดิสก์ของเซิร์ฟเวอร์เกิดเสียขึ้นมา คุณสามารถใช้ clone ตัวใดก็ได้เพื่อกู้ข้อมูลกลับไป ณ ตอนที่คุณทำการสร้าง clone นั้น (แต่คุณก็อาจเสีย server-side hooks ฯลฯ ที่มีอยู่ในเซิร์ฟเวอร์ไป )

คุณจะต้องใช้คำสั่ง git clone [url] เพื่อทำการ clone repository ยกตัวอย่างเช่น ถ้าคุณต้องการ clone ไลบรารี่ Ruby ที่ชื่อ Grit คุณสามารถทำได้โดยใช้คำสั่งดังนี้:

$ git clone git://github.com/schacon/grit.git
	คำสั่งดังกล่าวจะสร้างไดเรกทอรี่ชื่อ "grit" และสร้างไดเรกทอรี่ย่อยชื่อ .git 
	จากนั้นจะทำการดึงข้อมูลทั้งหมดทีมีอยู่ใน repository และ check out working copy เวอร์ชั่นล่าสุด ถ้าคุณดูใน grit 
	คุณจะเห็นแฟ้มที่อยู่ในโปรเจคทั้งหมดที่คุณสามารถเริ่มใช้งานได้ทันที ถ้าคุณต้องการ clone repository ไปที่ไดเรกทอรี่ชื่ออื่น คุณสามารถระบุชื่อที่คุณต้องการได้ต่อท้ายคำสั่งด้านบน:

$ git clone git://github.com/schacon/grit.git mygrit
คำสั่งนี้ทำงานเหมือนคำสั่งด้านบน แต่เก็บข้อมูลในไดเรกทอรี่ mygrit แทน Git มีโพรโทคอลสำหรับโอนข้อมูลหลายแบบ ตัวอย่างด้านบนใช้โพรโทคอล git:// แต่คุณสามารถใช้ http(s):// 
หรือ user@server:path.git ซึ่งใช้ SSH ได้เหมือนกัน ลองอ่านบทที่ 4 เพื่อดูวิธีตั้งค่าเครื่องเซิร์ฟเวอร์ของคุณ และข้อดีและข้อเสียของแต่ละโพรโตคอล