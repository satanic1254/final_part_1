# final_part_1
56660019

นายกรวิชญ์	เปลี่ยนเดชา	56660019	      กลุ่ม : 3403
1.ไม่เห็นด้วย เพราะ 
1.โปรแกรมเมอร์ แทบไม่ได้เจอกับ คนใช้งานเลย
2. การคุยงานก็คุยผ่านคนกลาง
3. .เมื่องานจบ ส่งเสร็จ หากใช้งานแล้วไม่ถูกใจบริษัทA การจะแก้ใหม่ เป็นเรื่องที่ยา่กสำหรับโปรแกรมเมอร์
----------------------------------------------------------------------------------------------------------------------------------
2. Version Control System คือ ระบบที่คอยจัดการ backup source code ของเรา โดยเก็บเป็นลักษณะ version ต่างๆ เช่นในกรณีเกิดปัญหาขึ้น ก็สามารถหยิบเอา source code ตัวเก่าที่เคยใช้งานได้มาแทน พูดง่ายๆ ก็คล้ายๆ กับ Undo ที่เราทำกันนั่นแหละ แต่ว่า Version Control ยังเป็นตัวกลางที่ทำให้ source code ของแต่ละเครื่อง (แต่ละ programmer) มี source code ที่ตรงกันด้วย ซึ่งโดยปกติทั่วไปแล้ว programmer มักจะทำโปรแกรมให้เสร็จสมบูรณ์ และใช้งานได้ก่อน จึงค่อยโยนขึ้นไปที่ repository เพื่อให้คนอื่นดึงไปใช้ต่อไป

Version Control ตัวที่เด่นดังอยู่ตอนนี้ก็มีอยู่ 2 ตัว คือ Subversion(SVN) และ Git ซึ่งผมเองก็ได้ใช้มาแล้วทั้ง 2 ตัว แต่จะเต็มรูปแบบกับ SVN ซะมากกว่า

Repository เป็นคำศัพท์ที่เจอได้บ่อยใน version control หมายถึง ที่เก็บ source code ของเรา ถ้าไม่มีก็ลองไปใช้บริการของ Google Code หรือ GitHub ก็ได้ครับ **ใครรู้จักตัวอื่นอีกก็ช่วยแนะนำด้วยนะครับ ^^

local / remote เป็นคำที่มักใช้เรียกแทน repository ในเครื่องเรา(local) และ repository บน server(remote) ซึ่ง remote จะเป็นตัวกลางระหว่างทีม


มาถึงเรื่องของ SVN กับ Git

การ pull โปรเจคลงมาจาก repository
SVN จะเป็นการ checkout โปรเจคลงมา ซึ่งหมายถึงว่า source code ที่เป็นเวอร์ชั่นล่าสุดจะถูกดึงลงมาไว้ที่เครื่องเรา
Git จะเป็นการ clone คือ การดึงมาทั้ง repository ไม่ว่าจะมีกิ่งก้านสาขาอะไรก็ตาม ทุกอย่างที่อยู่บน repository จะถูกเอาลงมาทั้งหมด

การ upload file สู่ repository
สำหรับ SVN นั้น จะเรียกว่าการ commit และหลังจากที่ commit ไปแล้วไฟล์เหล่านั้นก็จะอยู่ใน repository ทันที แต่ถ้าเป็น Git การ commit จะเป็นการเก็บอยู่ใน local ก่อน ซึ่งเราสามารถ commit แต่ละส่วนของโปรแกรมทีละนิดๆ แล้วค่อย push ขึ้นสู่ remote repository ทีเดียวก็ได้

ลำดับของ revision
SVN จะใช้เลขจำนวนเต็ม(Integer) รันไปเรื่อยๆ ซึ่งแน่นอนว่า ยิ่งเรา commit บ่อยเท่าไร ก็จะทำให้เลข revision มีเยอะขึ้นๆ
Git จะใช้ hash ด้วย SHA-1 hash algorithm เนื่องจาก git จะมีการ commit สู่ local repo. ก่อน เพราะถ้าใช้เป็นเลขรันไปเรื่อยๆเหมือน SVN ก็จะทำให้เกิดเลข revision ซ้ำกันได้


การทำงาน Online / Offline
SVN เป็น version control แบบ centralized หมายความว่า ทุกอย่างจะถูกเก็บในตัวกลาง ซึ่งก็คือ remote repo. ทั้งหมด ทำใช้งานจำเป็นต้องเชื่อมต่อ network ไปยัง repo. ไม่เช่นนั้นก็จะ commit หรือ check revision ก่อนๆ ไม่ได้เลย
Git เป็น version control แบบ distributed คือ หลังจากที่ clone remote repo. มาแล้ว ก็เท่ากับว่าเรามี local repo. ที่เหมือนกันกับ remote repo. ด้วย จะ commit ก็สามารถทำได้แบบ offline เลยเพราะเป็นการ commit ไปที่ local repo. แต่ถ้าเราจะ push ไปไว้ที่ remote repo. แน่นอนว่าต้องเชื่อมต่อ network เช่นเดียวกันครับ


เท่าที่ผมได้ลองใช้มาก็ประมาณนี้ครับ ประเด็นหลักๆ ผมว่าอยู่ที่การออกแบบที่แตกต่างกันระหว่าง Centralized กับ Distributed ซึ่งผมว่าแต่ละประเด็นมันก็แตกมาจากตรงนี้ ตัวไหนดีกว่า ตัวไหนเจ๋งกว่า ผมว่าอยู่ที่ปัจจัยหลายอย่าง วิธีการนำไปใช้ จำนวนคนในทีม ปริมาณงานที่ต้องแก้ไขร่วมกัน และอื่นๆ แต่ตอนนี้ผมใช้อยู่ทั้ง 2 ตัว SVN ใช้ที่ทำงาน ส่วน Git ใช้กับงานที่ตัวเองทำเล่นๆ เป็นการลอง Git ไปในตัวครับ ^^
  
-------------------------------------------------------------------------------------

3. git checkout -b [name_of_your_new_branch]
git push origin [name_of_your_new_branch]
git remote add [name_of_your_remote] 
git push [name_of_your_new_remote] [name_of_your_branch]
----------------------------------------------------------------------------------------
4. โดยปกติแล้ว git merge จะรวมโค๊ดให้เราเองอัตโนมัติ แต่ก็จะมีข้อยกเว้นเมื่อ แก้ไขไฟล์เดียวๆกัน ลองนึกถึงกรณีที่เราและเพื่อนร่วมทีม แก้ไขไฟล์เดียวกัน Git จะเกิดการ conflict เมื่อเราจะ merge โค๊ด โดยไม่รู้ว่าจะใช้โค๊ดของเราหรือของเพื่อน วิธีแก้ก็คือ ทำการ edit แล้ว commit ไปใหม่นั่นเอง
---------------------------------------------------------------------------------------
5. ('a'..'e')¬.each {|ch|¬ print¬ ch}
=> "a".."e"
Success!
-----------------------------------------------------------------------------------------
6. การใช้งานคอมพิวเตอร์ต้องมีซอฟตืแวร์ประยุกต์ ซึ่งอาจเป็นซอฟต์แวร์สำเร็จที่มีผู้พัฒนาเพื่อใช้งานทั่วไปทำให้ทำงานได้สะดวกขึ้น หรืออาจเป็นซอฟต์แวร์ใช้งานเฉพาะ ซึ่งผู้ใช้เป็นผู้พัฒนาขึ้นเองเพื่อให้เหมาะสมกับสภาพการทำงานของตน
-----------------------------------------------------------------------------------------
7. MVC นั้นย่อมาจาก Model View Controller ซึ่งเป็นส่วนประกอบของ Web Framework ในปัจจุบัน เช่น Ruby On Rails, Yii2 PHP Framework โดยแต่ละส่วนนั้นมีหน้าที่หลักๆ ดังนี้

-----------------------------------------------------------------------------------------
1.	Model มีหน้าที่หลักในการจัดการเกี่ยวกับฐานข้อมูล โดยจะมี ORM (Object Relational Mapping) เข้ามาช่วยในการทำงาน โดย ORM จะช่วยแปลง ฐานข้อมูล เป็น Object และแปลง Object เป็น ฐานข้อมูล โดยที่เราไม่จำเป็นต้องเขียน SQL เพราะตัว ORM จะช่วยแปลงการเรียกใช้งาน Method ของ Object ไปเป็น SQL เอง
2.	View คือส่วนในการแสดงผลหน้าเว็บ โดยส่วนใหญ่จะเป็นโค้ดภาษา HTML และ CSS
3.	Controller จะเป็นตัวจัดการความต้องการของ User เช่น ถ้า User ต้องการดูหน้าเว็บ ตัว Controller จะไปเรียก View มาเพื่อแสดงผลตามที่ User ต้องการ หรือถ้า User ต้องการดูข้อมูล, แก้ไขข้อมูล, หรือลบข้อมูลในฐานข้อมูล ตัว Controller ก็จะไปเรียกใช้งาน Method ต่างๆ ใน Model เพื่อจัดการกับฐานข้อมูลตามความต้องการของ User โดยสรุปแล้ว Controller จะเป็นส่วนที่เชื่อมต่อให้ View และ Model ทำงานร่วมกัน
หลักการเบื้องต้นของ MVC ก็มีเพียงเท่านี้
------------------------------------------------------------------------------------------
8. CodeIgniter ดีกว่า เพราะ
1.	การติดตั้ง Ruby on Rails บนเครื่อง development ยุ่งยากกว่าเครื่องมืออื่นๆ เช่น PHP, Java หรือ .NET
2.	การ Deploy Rails application ขึ้นเซิร์ฟเวอร์จริง ก็ยิ่งยุ่งยากมากกว่าการติดตั้งบนเครื่อง development
3.	ความเร็วในการทำงานของภาษา Ruby จัดได้ว่าช้ากว่าคู่แข่งอยู่มาก มีความพยายาม แก้ปัญหานี้จากหลายๆ ฝ่าย เช่น JRuby เป็นการใช้ Java Virtual Machine มารันโปรแกรมที่เขียนขึ้นด้วยภาษา Ruby อาศัยการทำงานของ Java Hotspot Compiler ในการช่วยเพิ่มความเร็วในการทำงาน
4.	ทั้ง Ruby และ Ruby on Rails มีทัศนคติที่ไม่ดีกับ Microsoft Windows การส่งเสริมการ ทำงานบน Windows จึงมีไม่มากนัก ทำให้การพัฒนา Ruby on Rails ต้องทำบน Linux หรือ Apple Mac OS เป็นหลักและ Deploy ขึ้น Linux Server เป็นหลัก
5.	Ruby on Rails ได้รับความนิยมมากในต่างประเทศ แต่ในประเทศไทยเพิ่งเริ่มมีความนิยมในระยะเวลา 1-2 ปีมานี้ ทำให้ตำรับตำราต่างๆ เป็นภาษาต่างประเทศทั้งหมด
--------------------------------------------------------------------------------------------
9. อะไรคือ Heroku? และ เราจะใช้มันทําไรได้ละ?
ถ้าใครเขียนเว็ปที่ไม่ใช่ภาษา php มาแล้วต้องการหา hosting เพื่อเป็น production server เอง โดยที่ไม่ได้ตั้ง server เอง จะเข้าใจเลยว่า มันลําบากน่ะ … hosting ส่วนใหญ่ที่เคยเจอมักจะไม่รองรับ ภาษาอื่นนอกจาก php ซักเท่าไร ทําให้คนที่ชอบเล่น ชอบลองของแปลกอย่างเราเอง ก็หา host มาเล่นลําบาก จะตั้ง sever เองก็เกินตัวไป ดังนั้น เค้าถึงมี
 Cloud Application Platform
ออกมากันอย่างหลากหลายเลยในช่วงนี้ เจ้าดังๆที่หลายคนน่าจะรู้จักก็ Amazon Web Services , Google Cloud Platform แต่ที่ผมสนใจ และ เหมาะสมที่สุดกับตับเอง ก็ไม่พ้น Heroku นั่นเอง … ด้วยเหตุผลที่มันฟรี และ สามารถใช้ Node.js ได้ ( รวมถึงมี add-on สําหรับ database หรืออื่นๆ ให้เราเลย เช่น MongoHQ ทําให้เราไม่ต้องเสียเวลากับเรื่องนี้ และไปใส่ใจอย่างอื่นได้เต็มที่) และ นั่นคือ Heroku และที่มาของมันPlatform as a Services ( PaaS )
แล้วจะเริ่มต้นกับ Heroku ยังไงดี?
ไม่ยากเย็นเลย แค่ใช้ git push repo เราไปที่ heroku + สร้าง config ไฟล์ด้วย foreman ( Proficle ไฟล์) แค่นั้นเอง มันก็จะทํางานให้เรา
โดยการจะ push ไปที่ heroku นั้น ทาง heroku เองจะมี  toolbelt  เป็น Heroku Client มาให้เราใช้ ซึ่งจะมีทุก platform เลย ไม่ว่าจะเป็น (window ,osx ,linux) แล้วใน toolbelt มันจะมี foreman ติดตั้งมาด้วย ซึ่งมันจะทําหน้าที่เป็น config file ว่าจะให้  Heroku ทํางานยังไง และ มองตัวไหนเป็นตัวที่มันจะเป็นไฟล์หลัก เช่นถ้าเป็น Node.js ก็จะออกมาแนวข้างล่างนี้
web: node server.js
แล้วพอเรา Push ( git ) ไปที่ Heroku มันก็จะเริ่มทํางานด้วยไฟล์นี้นั่นเอง Node.js Tutorial with Heroku
FYI : เจ้า Foreman (ไฟล์ Proficle) ตัวนี้ยังสามารถสั่งให้ application หลายๆตัว ทํางานได้ด้วย เช่น
web: bundle exec thin start -p $PORT
worker: bundle exec rake resque:work QUEUE=*
clock: bundle exec rake resque:scheduler
เค้าตั้งชื่อ Foreman === หัวหน้าคนงาน ซึ่งสมเหตุผลดีน่ะ คือ เป็นคนบอกคนงานให้ทําไรบ้าง ว่างั้นเหอะ Blog คนทํา
ส่วนจะทําให้ Application เราทํางานบน heroku ได้แล้ว นอกจาก config file ของ foreman (ไฟล์ Proficle) แล้วก็ต้อง create app และ add git remote ของ heroku เข้าไป
heroku apps:create appname
ซึ่งพอเราใช้คําสั่งนี้ มันจะสร้าง app บน heroku ให้ และ add remote ลง config ของ git ให้เราเลย หลังจากนั้น เราก็ push ขึ้น heroku ได้เลย
git push heroku master
แล้วก็รอมัน setting application ให้เราเท่านั้นแหละ พอมันเสร็จก็เปิดดูได้เลยน่ะ ด้วยคําสั่งนี้
heroku open
จบอย่างสวยงาม ก็จะเห็น application เราทํางานล่ะ
มี Application ตัวอย่างไหม?
มี app ตัวนึง ลองทําเล่นๆขึ้นมาชื่อ vchat ซึ่ง code อยู่ที่ github repo และ application ที่ on air อยู่ที่ vchat demo on heroku
ข้อควรระวัง เมื่อทํางานกับ Heroku
•	Heroku ใช้ Git ในการ push ขึ้นไปที่ Repository มัน แต่มันรับเฉพาะ master branch เท่านั้นน่ะ เหมือนจะไม่รับตัวอื่นนะ
•	ถ้าเราทํา Node.js มันจะมี ให้ระบุ Port ใช่ไหมล่ะ แนะนําใช้ ยังงี้จะได้เป็น dynamic นิดๆ ไม่ static ไป( process.env.PORT || 5000 ) ส่วน Node client ก็ใช้ DNS แทนน่ะ
•	MongoHQ ไม่ให้ สิทธิ์ Admin กับเราหรอกน่ะ เพราะฉะนั้นคําสั่งของ MongoDB จะถูกลดไปเยอะเช่น show dbs เป็นต้นจ้า ใช้อื่นๆแทนน่ะ
•	ถ้าจะดู Logs ก็ใช้คําสั่ง heroku logs -t น่ะ จะได้เห็นว่า application เราเป็นไงบ้าง เพียงแต่ต้องเข้าไปใน folder app เราก่อนน่ะ
-----------------------------------------------------------------------------------------------------
10. เป็นกระบวนการที่ช่วยส่งเสริมให้นักพัฒนาซอฟต์แวร์สามารถพัฒนาคุณภาพของ กระบวนการพัฒนาซอฟต์แวร์ของตนเอง โดยเน้นการจัดการข้อผิดพลาด และพัฒนาทักษะการประมาณและวางแผนให้อย่างถูกต้อง แม่นยา และมีคุณภาพมากขึ้น
--------------------------------------------------------------------------------------------------------


