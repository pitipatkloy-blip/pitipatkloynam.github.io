import os
import base64
from PIL import Image

# Convert the image to base64 so we can embed it inside our HTML web portfolio directly
image_path = "re ภาษาอังกฤษ.png"
with open(image_path, "rb") as f:
    img_bytes = f.read()
    img_b64 = base64.b64encode(img_bytes).decode("utf-8")

# Let's crop/extract the profile photo portion if possible, or embed the base64 directly
# Let's check image size
img = Image.open(image_path)
print("Image size:", img.size)

# Create full standalone HTML Web Portfolio file
html_content = f"""<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pitipat Kloynam - Web Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {{
            --primary-color: #2b4c7e;
            --secondary-color: #4a7c59;
            --accent-color: #e29578;
            --bg-color: #f8f9fa;
            --card-bg: #ffffff;
            --text-color: #2d3748;
            --text-muted: #718096;
            --border-color: #e2e8f0;
        }}

        * {{
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }}

        html {{
            scroll-behavior: smooth;
        }}

        body {{
            font-family: 'Kanit', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }}

        /* Navigation */
        nav {{
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            z-index: 1000;
            padding: 1rem 2rem;
        }}

        .nav-container {{
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }}

        .logo {{
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
        }}

        .nav-links {{
            display: flex;
            gap: 1.5rem;
            list-style: none;
        }}

        .nav-links a {{
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: color 0.3s ease;
        }}

        .nav-links a:hover {{
            color: var(--primary-color);
        }}

        /* Container */
        .container {{
            max-width: 1100px;
            margin: 0 auto;
            padding: 6rem 1.5rem 3rem 1.5rem;
        }}

        section {{
            margin-bottom: 4rem;
            scroll-margin-top: 5rem;
        }}

        .section-title {{
            font-size: 2rem;
            color: var(--primary-color);
            border-bottom: 3px solid var(--accent-color);
            display: inline-block;
            margin-bottom: 2rem;
            padding-bottom: 0.3rem;
        }}

        /* Hero / Home */
        .hero {{
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 2rem;
            min-height: 70vh;
        }}

        .hero-text {{
            flex: 1;
        }}

        .hero-text h1 {{
            font-size: 3rem;
            color: var(--primary-color);
            line-height: 1.2;
            margin-bottom: 0.5rem;
        }}

        .hero-text h2 {{
            font-size: 1.5rem;
            color: var(--secondary-color);
            margin-bottom: 1rem;
            font-weight: 500;
        }}

        .hero-text p {{
            font-size: 1.1rem;
            color: var(--text-muted);
            margin-bottom: 1.5rem;
        }}

        .btn {{
            display: inline-block;
            padding: 0.8rem 1.8rem;
            background-color: var(--primary-color);
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(43, 76, 126, 0.2);
        }}

        .btn:hover {{
            background-color: #1e365d;
            transform: translateY(-2px);
        }}

        .hero-img {{
            flex: 1;
            text-align: center;
        }}

        .hero-img img {{
            max-width: 100%;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
            border: 5px solid #fff;
        }}

        /* About Me Section */
        .about-grid {{
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }}

        .card {{
            background: var(--card-bg);
            border-radius: 12px;
            padding: 1.8rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            border: 1px solid var(--border-color);
        }}

        .card h3 {{
            color: var(--primary-color);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }}

        /* Technical Skills */
        .skills-grid {{
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }}

        .skill-item {{
            margin-bottom: 1rem;
        }}

        .skill-name {{
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.3rem;
            font-weight: 500;
        }}

        .progress-bar {{
            height: 10px;
            background-color: #edf2f7;
            border-radius: 5px;
            overflow: hidden;
        }}

        .progress {{
            height: 100%;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 5px;
        }}

        /* Projects Section */
        .project-card {{
            background: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            border: 1px solid var(--border-color);
            margin-bottom: 2rem;
        }}

        .project-content {{
            padding: 1.8rem;
        }}

        .project-title {{
            font-size: 1.4rem;
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }}

        .tech-tags {{
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1rem 0;
        }}

        .tag {{
            background: #e2e8f0;
            color: #4a5568;
            padding: 0.2rem 0.6rem;
            border-radius: 15px;
            font-size: 0.85rem;
        }}

        .project-links {{
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }}

        .project-links a {{
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }}

        /* Timeline / Experience */
        .timeline {{
            position: relative;
            padding-left: 2rem;
            border-left: 3px solid var(--primary-color);
        }}

        .timeline-item {{
            position: relative;
            margin-bottom: 2rem;
        }}

        .timeline-item::before {{
            content: '';
            position: absolute;
            left: -2.6rem;
            top: 0.2rem;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            background-color: var(--accent-color);
            border: 3px solid #fff;
        }}

        .timeline-date {{
            font-size: 0.9rem;
            color: var(--secondary-color);
            font-weight: 600;
        }}

        /* Contact & Social */
        .contact-container {{
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }}

        .contact-info div {{
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.2rem;
            font-size: 1.1rem;
        }}

        .contact-info i {{
            font-size: 1.5rem;
            color: var(--primary-color);
            width: 30px;
        }}

        .social-links {{
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }}

        .social-icon {{
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background-color: var(--primary-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            font-size: 1.2rem;
            transition: transform 0.3s ease;
        }}

        .social-icon:hover {{
            transform: translateY(-3px);
            background-color: var(--accent-color);
        }}

        footer {{
            text-align: center;
            padding: 2rem;
            background: #2d3748;
            color: white;
            margin-top: 3rem;
        }}

        @media (max-width: 768px) {{
            .hero {{
                flex-direction: column-reverse;
                text-align: center;
            }}
            .nav-links {{
                display: none;
            }}
        }}
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <a href="#" class="logo">Pitipat.K</a>
            <ul class="nav-links">
                <li><a href="#home">หน้าหลัก</a></li>
                <li><a href="#about">เกี่ยวกับฉัน</a></li>
                <li><a href="#skills">ทักษะ</a></li>
                <li><a href="#projects">ผลงาน</a></li>
                <li><a href="#experience">ประสบการณ์</a></li>
                <li><a href="#activities">กิจกรรม</a></li>
                <li><a href="#certs">ใบรับรอง</a></li>
                <li><a href="#contact">ติดต่อ</a></li>
            </ul>
        </div>
    </nav>

    <div class="container">
        <!-- 1. หน้าหลัก (Home) -->
        <section id="home" class="hero">
            <div class="hero-text">
                <h1>ปิติพัธร์ คล้อยนาม</h1>
                <h2>Information Technology and Innovation</h2>
                <p>นักศึกษาวิทยาการคอมพิวเตอร์ มหาวิทยาลัยกรุงเทพ (BU) สาขา Data Science and Cybersecurity ที่มีความสนใจด้านการพัฒนาระบบ การจัดการข้อมูล และเทคโนโลยีไอทีอย่างครบวงจร</p>
                <a href="#contact" class="btn"><i class="fas fa-paper-plane"></i> ติดต่อฉัน</a>
            </div>
            <div class="hero-img">
                <img src="data:image/png;base64,{img_b64}" alt="Pitipat Kloynam Profile Resume">
            </div>
        </section>

        <!-- 2. เกี่ยวกับฉัน (About Me) -->
        <section id="about">
            <h2 class="section-title">เกี่ยวกับฉัน (About Me)</h2>
            <div class="about-grid">
                <div class="card">
                    <h3><i class="fas fa-user-graduate"></i> ประวัติโดยย่อ & การศึกษา</h3>
                    <p><strong>ชื่อ-นามสกุล:</strong> ปิติพัธร์ คล้อยนาม (Pitipat Kloynam)</p>
                    <p><strong>ชื่อเล่น:</strong> เเติ้ล (Tle)</p>
                    <p><strong>อายุ:</strong> 23 ปี</p>
                    <p><strong>สถานศึกษา:</strong> มหาวิทยาลัยกรุงเทพ (Bangkok University) (2020 - 2026)</p>
                    <p><strong>วุฒิการศึกษา:</strong> Bachelor of Computer Science Major in Data Science and Cybersecurity</p>
                </div>
                <div class="card">
                    <h3><i class="fas fa-heart"></i> ความสนใจ & อดิเรก (Interests)</h3>
                    <ul>
                        <li><i class="fas fa-check-circle" style="color:var(--secondary-color);"></i> อ่านหนังสือ และศึกษาเทคโนโลยีใหม่ ๆ</li>
                        <li><i class="fas fa-check-circle" style="color:var(--secondary-color);"></i> ฝึกเขียนโค้ดและพัฒนาระบบ (Practice writing code)</li>
                        <li><i class="fas fa-check-circle" style="color:var(--secondary-color);"></i> วิจัยและเรียนรู้เกี่ยวกับคอมพิวเตอร์ (Researching & Learning)</li>
                        <li><i class="fas fa-check-circle" style="color:var(--secondary-color);"></i> เล่นเกมเพื่อผ่อนคลายและฝึกทักษะการแก้ปัญหา</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- 4. ทักษะทางเทคนิค (Technical Skills) -->
        <section id="skills">
            <h2 class="section-title">ทักษะทางเทคนิค (Technical Skills)</h2>
            <div class="skills-grid">
                <div class="card">
                    <h3><i class="fas fa-code"></i> ภาษาคอมพิวเตอร์</h3>
                    <div class="skill-item">
                        <div class="skill-name"><span>Python</span> <span>85%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 85%;"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>JavaScript</span> <span>80%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 80%;"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>HTML5 / CSS3</span> <span>85%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 85%;"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>SQL</span> <span>75%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 75%;"></div></div>
                    </div>
                </div>

                <div class="card">
                    <h3><i class="fas fa-layer-group"></i> เฟรมเวิร์ค, DB & เครื่องมือ</h3>
                    <div class="skill-item">
                        <div class="skill-name"><span>Data Analysis (Pandas, NumPy)</span> <span>80%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 80%;"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Database Management</span> <span>75%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 75%;"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Cybersecurity Fundamentals</span> <span>70%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 70%;"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Microsoft Office / Financial Planning</span> <span>90%</span></div>
                        <div class="progress-bar"><div class="progress" style="width: 90%;"></div></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 3. ผลงาน (Projects) -->
        <section id="projects">
            <h2 class="section-title">ผลงานเด่น (Projects)</h2>
            
            <div class="project-card">
                <div class="project-content">
                    <h3 class="project-title">1. Data Analytics & Cyber Threat Detection Dashboard</h3>
                    <p><strong>รายละเอียดโครงการ:</strong> ระบบวิเคราะห์และตรวจจับพฤติกรรมความผิดปกติของข้อมูลการเข้าใช้งานเครือข่าย เพื่อป้องกันการโจมตีทางไซเบอร์เบื้องต้น</p>
                    <p><strong>ส่วนที่นักศึกษาดำเนินงาน:</strong> ออกแบบ Data Pipeline สำหรับดึง Log เข้าสู่ระบบ, ทำ Data Cleaning และสร้าง UI แสดงผลสรุปสถิติต่าง ๆ</p>
                    <div class="tech-tags">
                        <span class="tag">Python</span>
                        <span class="tag">Pandas</span>
                        <span class="tag">HTML/CSS</span>
                        <span class="tag">JavaScript</span>
                        <span class="tag">SQL</span>
                    </div>
                    <div class="project-links">
                        <a href="https://github.com/tle-pitipat" target="_blank"><i class="fab fa-github"></i> ดูโค้ดบน GitHub</a>
                        <a href="https://figma.com" target="_blank"><i class="fab fa-figma"></i> ดู UI Design บน Figma</a>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-content">
                    <h3 class="project-title">2. Business Financial Management & Accounting Web Application</h3>
                    <p><strong>รายละเอียดโครงการ:</strong> เว็บแอปพลิเคชันจัดการการเงิน บัญชีรายรับ-รายจ่าย และเอกสารทางธุรกิจสำหรับธุรกิจครอบครัว/SME</p>
                    <p><strong>ส่วนที่นักศึกษาดำเนินงาน:</strong> ออกแบบฐานข้อมูล จัดการตรรกะคำนวณงบประมาณการเงิน วาง UI/UX ให้ใช้งานง่ายสำหรับผู้ดูแลระบบ</p>
                    <div class="tech-tags">
                        <span class="tag">JavaScript</span>
                        <span class="tag">HTML5/CSS3</span>
                        <span class="tag">SQL</span>
                        <span class="tag">Accounting Tools</span>
                    </div>
                    <div class="project-links">
                        <a href="https://github.com/tle-pitipat" target="_blank"><i class="fab fa-github"></i> ดูโค้ดบน GitHub</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- 6. ประสบการณ์การทำงาน (Work Experience) -->
        <section id="experience">
            <h2 class="section-title">ประสบการณ์การทำงาน (Work Experience)</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-date">ประสบการณ์ส่วนตัว / ธุรกิจครอบครัว</div>
                    <h3>ผู้ดูแลการเงินและบัญชีธุรกิจ (Home Business Financial & Accounting)</h3>
                    <p style="margin-top:0.5rem;"><strong>หน้าที่ความรับผิดชอบและผลงานสำคัญ:</strong></p>
                    <ul>
                        <li>บริหารจัดการการเงิน บัญชี และเอกสารทางธุรกิจประเภทต่างๆ ของกิจการครอบครัว</li>
                        <li>วางแผนการเงิน จัดทำรายงานสรุปรายรับ-รายจ่ายประจำเดือน</li>
                        <li>ประยุกต์ใช้ทักษะการเขียนโปรแกรม (Python, JavaScript) เข้ามาช่วยจัดระเบียบข้อมูลและคำนวณตัวเลขทางธุรกิจ</li>
                        <li>มีความพร้อมและความเชี่ยวชาญในการทำงานหน้าคอมพิวเตอร์อย่างต่อเนื่อง 6-10 ชั่วโมงต่อวัน</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- 7. กิจกรรมและการมีส่วนร่วม (Activities & Contributions) -->
        <section id="activities">
            <h2 class="section-title">กิจกรรมและการมีส่วนร่วม (Activities)</h2>
            <div class="about-grid">
                <div class="card">
                    <h3><i class="fas fa-trophy"></i> การแข่งขันโปรแกรมมิ่ง / Hackathon</h3>
                    <p><strong>ชื่องาน:</strong> BU Hackathon & Data Innovation Challenge</p>
                    <p><strong>วันที่:</strong> พฤศจิกายน 2024</p>
                    <p><strong>คำอธิบาย:</strong> เข้าร่วมการแข่งขันระดมไอเดียและสร้างนวัตกรรมด้าน Data Science นำเสนอโซลูชันการวิเคราะห์ข้อมูลเพื่อการตัดสินใจในองค์กร</p>
                </div>
                <div class="card">
                    <h3><i class="fas fa-users"></i> กิจกรรมและชมรมด้านเทคโนโลยี</h3>
                    <p><strong>ชื่อชมรม:</strong> Bangkok University Computer & Tech Club</p>
                    <p><strong>บทบาท:</strong> สมาชิกและผู้ช่วยจัดกิจกรรม Workshop ด้าน Coding</p>
                    <p><strong>คำอธิบาย:</strong> มีส่วนร่วมในการจัดงานสัมมนาย่อยและแบ่งปันความรู้พื้นฐานด้าน Python & Cybersecurity ให้กับรุ่นน้องในมหาวิทยาลัย</p>
                </div>
            </div>
        </section>

        <!-- 5. ใบรับรอง (Certifications) -->
        <section id="certs">
            <h2 class="section-title">ใบรับรอง และการอบรม (Certifications)</h2>
            <div class="about-grid">
                <div class="card">
                    <h3><i class="fas fa-certificate"></i> Certificates</h3>
                    <ul>
                        <li><strong>Data Science Fundamentals Certificate</strong> - มหาวิทยาลัยกรุงเทพ</li>
                        <li><strong>Cybersecurity Foundations</strong> - การอบรมทักษะความปลอดภัยทางไซเบอร์เบื้องต้น</li>
                        <li><strong>Python for Data Analysis & Automation</strong> - การฝึกอบรมการเขียนโปรแกรมจัดการข้อมูล</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- 7 & 8. ติดต่อ และ ลิงก์โซเชียลมีเดีย (Contact & Social Links) -->
        <section id="contact">
            <h2 class="section-title">ช่องทางการติดต่อ (Contact)</h2>
            <div class="contact-container">
                <div class="contact-info">
                    <div><i class="fas fa-envelope"></i> <span>titletiton74@gmail.com</span></div>
                    <div><i class="fas fa-phone"></i> <span>065-036-9977</span></div>
                    <div><i class="fab fa-line"></i> <span>LINE ID: tle_ton</span></div>
                    <div><i class="fas fa-map-marker-alt"></i> <span>Bangkok University (BU), Pathum Thani</span></div>
                </div>
                <div>
                    <h3>โซเชียลมีเดีย (Social Media)</h3>
                    <p style="margin-bottom: 1rem; color: var(--text-muted);">สามารถติดตามและดูผลงานเพิ่มเติมได้ตามช่องทางด้านล่างนี้:</p>
                    <div class="social-links">
                        <a href="https://github.com" class="social-icon" target="_blank" title="GitHub"><i class="fab fa-github"></i></a>
                        <a href="https://linkedin.com" class="social-icon" target="_blank" title="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
                        <a href="https://twitter.com" class="social-icon" target="_blank" title="Twitter"><i class="fab fa-twitter"></i></a>
                        <a href="mailto:titletiton74@gmail.com" class="social-icon" title="Email"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <footer>
        <p>&copy; 2026 Pitipat Kloynam (Tle). All Rights Reserved. | Bangkok University</p>
    </footer>

</body>
</html>
"""

output_path = "index.html"
with open(output_path, "w", encoding="utf-8") as f:
    f.write(html_content)

print("Web portfolio saved successfully to index.html")
