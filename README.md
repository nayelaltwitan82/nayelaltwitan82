## Hi there 👋

<!--
**nayelaltwitan82/nayelaltwitan82** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
--><!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام الحجز | الجنات السبع لعقل لا يتوقف</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --blood-red: #8b0000;
            --dark-soul: #0a0a12;
            --golden-key: #d4af37;
            --ancient-parchment: #f5e9c9;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: var(--dark-soul);
            color: #f0f0f0;
            overflow-x: hidden;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="none"/><path d="M0,50 Q50,0 100,50 Q50,100 0,50" stroke="rgba(139, 0, 0, 0.1)" fill="none"/></svg>');
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* تصميم نظام الحجز */
        .booking-system {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            margin: 50px 0;
            background: rgba(20, 20, 30, 0.8);
            padding: 30px;
            border: 1px solid var(--blood-red);
            box-shadow: 0 0 20px rgba(139, 0, 0, 0.3);
        }
        
        .booking-steps {
            flex: 1;
            min-width: 300px;
        }
        
        .booking-summary {
            flex: 1;
            min-width: 300px;
            background: rgba(10, 10, 18, 0.9);
            padding: 25px;
            border: 1px solid var(--golden-key);
            position: relative;
        }
        
        .step {
            margin-bottom: 30px;
            padding: 20px;
            border-left: 3px solid var(--golden-key);
            background: rgba(30, 30, 40, 0.6);
            display: none;
        }
        
        .step.active {
            display: block;
        }
        
        .step-title {
            color: var(--golden-key);
            margin-bottom: 20px;
            font-size: 1.5rem;
            position: relative;
        }
        
        .step-title::after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--blood-red);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            color: #aaa;
        }
        
        input, select, textarea {
            width: 100%;
            padding: 12px;
            background: #111;
            color: white;
            border: 1px solid #444;
            border-radius: 0;
            font-size: 1rem;
        }
        
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--golden-key);
        }
        
        .btn {
            background: linear-gradient(45deg, var(--dark-soul), var(--blood-red));
            color: white;
            font-size: 1rem;
            padding: 12px 30px;
            border: 2px solid var(--golden-key);
            cursor: pointer;
            transition: all 0.4s;
            display: inline-block;
            text-align: center;
            margin-top: 10px;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(139, 0, 0, 0.5);
        }
        
        .btn-full {
            width: 100%;
            padding: 15px;
            font-size: 1.1rem;
        }
        
        .btn-group {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .summary-title {
            text-align: center;
            color: var(--golden-key);
            margin-bottom: 20px;
            font-size: 1.8rem;
            border-bottom: 1px solid var(--blood-red);
            padding-bottom: 10px;
        }
        
        .summary-item {
            display: flex;
            justify-content: space-between;
            padding: 12px 0;
            border-bottom: 1px dashed #444;
        }
        
        .summary-item:last-child {
            border-bottom: none;
            font-weight: bold;
            color: var(--golden-key);
            font-size: 1.2rem;
            margin-top: 10px;
        }
        
        .product-image {
            width: 100%;
            height: 200px;
            background: url('https://images.unsplash.com/photo-1495640388908-05fa85288e61?auto=format&fit=crop&w=1950') center/cover;
            margin: 20px 0;
            border: 2px solid var(--blood-red);
            position: relative;
        }
        
        .product-image::after {
            content: "النسخة الموقعة والملطخة";
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(139, 0, 0, 0.8);
            padding: 5px;
            text-align: center;
            font-size: 0.9rem;
        }
        
        .seal {
            position: absolute;
            top: -15px;
            right: -15px;
            width: 60px;
            height: 60px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="45" fill="none" stroke="%23d4af37" stroke-width="2"/><path d="M30,50 Q50,30 70,50 Q50,70 30,50 Z" fill="%238b0000" opacity="0.7"/></svg>') center/contain no-repeat;
        }
        
        .confirmation {
            display: none;
            text-align: center;
            padding: 40px;
            background: rgba(10, 10, 18, 0.9);
            border: 2px solid var(--golden-key);
            margin: 50px 0;
        }
        
        .confirmation.active {
            display: block;
        }
        
        .confirmation-icon {
            font-size: 4rem;
            color: var(--golden-key);
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        .confirmation h2 {
            color: var(--golden-key);
            font-size: 2.5rem;
            margin-bottom: 20px;
        }
        
        .confirmation p {
            font-size: 1.2rem;
            margin-bottom: 15px;
            line-height: 1.6;
        }
        
        .confirmation-code {
            background: rgba(139, 0, 0, 0.3);
            padding: 15px;
            font-family: monospace;
            font-size: 1.5rem;
            letter-spacing: 3px;
            margin: 20px 0;
            border: 1px solid var(--golden-key);
            display: inline-block;
        }
        
        .hidden-field {
            display: none;
        }
        
        /* التكيف مع الجوالات */
        @media (max-width: 768px) {
            .booking-system {
                flex-direction: column;
            }
            
            .btn-group {
                flex-direction: column;
            }
            
            .btn {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 style="text-align: center; margin: 40px 0; color: var(--golden-key); font-size: 2.8rem;">
            <i class="fas fa-lock"></i> حجز النسخة الموقعة من "الجنات السبع"
        </h1>
        
        <div class="booking-system">
            <div class="booking-steps">
                <!-- الخطوة 1: معلومات الحجز -->
                <div class="step active" id="step1">
                    <h2 class="step-title">معلومات الحجز</h2>
                    <div class="form-group">
                        <label for="fullName"><i class="fas fa-user"></i> الاسم الكامل</label>
                        <input type="text" id="fullName" required placeholder="اكتب اسمك كما تريد ظهوره على الإهداء">
                    </div>
                    
                    <div class="form-group">
                        <label for="email"><i class="fas fa-envelope"></i> البريد الإلكتروني</label>
                        <input type="email" id="email" required placeholder="example@domain.com">
                    </div>
                    
                    <div class="form-group">
                        <label for="phone"><i class="fas fa-phone"></i> رقم الهاتف</label>
                        <input type="tel" id="phone" required placeholder="05XXXXXXXX">
                    </div>
                    
                    <div class="form-group">
                        <label for="country"><i class="fas fa-globe"></i> الدولة</label>
                        <select id="country" required>
                            <option value="">-- اختر الدولة --</option>
                            <option value="SA">المملكة العربية السعودية</option>
                            <option value="AE">الإمارات العربية المتحدة</option>
                            <option value="KW">الكويت</option>
                            <option value="QA">قطر</option>
                            <option value="OM">عُمان</option>
                            <option value="BH">البحرين</option>
                            <option value="EG">مصر</option>
                            <option value="other">دولة أخرى</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="address"><i class="fas fa-map-marker-alt"></i> العنوان الكامل</label>
                        <textarea id="address" rows="3" required placeholder="الشارع، المدينة، الرمز البريدي"></textarea>
                    </div>
                    
                    <div class="form-group">
                        <label for="message"><i class="fas fa-pen"></i> رسالة خاصة على النسخة الموقعة (اختياري)</label>
                        <textarea id="message" rows="3" placeholder="اكتب رسالتك الخاصة التي ستظهر مع توقيع المؤلف"></textarea>
                    </div>
                    
                    <div class="btn-group">
                        <button class="btn" onclick="nextStep(2)">التالي <i class="fas fa-arrow-left"></i></button>
                    </div>
                </div>
                
                <!-- الخطوة 2: خيارات النسخة -->
                <div class="step" id="step2">
                    <h2 class="step-title">خيارات النسخة</h2>
                    
                    <div class="form-group">
                        <label><i class="fas fa-book"></i> نوع النسخة</label>
                        <div style="display: flex; gap: 15px; margin-top: 10px;">
                            <label style="flex: 1; background: rgba(30, 30, 40, 0.6); padding: 15px; cursor: pointer;">
                                <input type="radio" name="edition" value="standard" checked style="margin-left: 10px;">
                                النسخة القياسية ($49)
                                <div style="font-size: 0.9rem; color: #aaa; margin-top: 5px;">الكتاب فقط</div>
                            </label>
                            <label style="flex: 1; background: rgba(30, 30, 40, 0.6); padding: 15px; cursor: pointer; border: 2px solid var(--golden-key);">
                                <input type="radio" name="edition" value="deluxe" style="margin-left: 10px;">
                                النسخة الفاخرة ($79)
                                <div style="font-size: 0.9rem; color: var(--golden-key); margin-top: 5px;">الكتاب + خريطة الجنات + شهادة</div>
                            </label>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label><i class="fas fa-tint"></i> لون البقع</label>
                        <div style="display: flex; gap: 10px; margin-top: 10px; flex-wrap: wrap;">
                            <label style="background: #8b0000; padding: 10px 15px; cursor: pointer;">
                                <input type="radio" name="stain" value="red" checked style="margin-left: 5px;">
                                أحمر دموي
                            </label>
                            <label style="background: #d4af37; padding: 10px 15px; cursor: pointer;">
                                <input type="radio" name="stain" value="gold" style="margin-left: 5px;">
                                ذهبي غامض
                            </label>
                            <label style="background: #2a2a40; padding: 10px 15px; cursor: pointer;">
                                <input type="radio" name="stain" value="dark" style="margin-left: 5px;">
                                أزرق ليلي
                            </label>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="packaging"><i class="fas fa-gift"></i> نوع التغليف</label>
                        <select id="packaging" required>
                            <option value="standard">التغليف القياسي (مجاني)</option>
                            <option value="mystery">صندوق الغموض (+$15)</option>
                            <option value="premium">التغليف الفاخر (+$25)</option>
                        </select>
                    </div>
                    
                    <div class="btn-group">
                        <button class="btn" onclick="prevStep(1)"><i class="fas fa-arrow-right"></i> السابق</button>
                        <button class="btn" onclick="nextStep(3)">التالي <i class="fas fa-arrow-left"></i></button>
                    </div>
                </div>
                
                <!-- الخطوة 3: الدفع والتأكيد -->
                <div class="step" id="step3">
                    <h2 class="step-title">طريقة الدفع</h2>
                    
                    <div class="form-group">
                        <label><i class="fas fa-credit-card"></i> طريقة الدفع</label>
                        <div style="display: flex; gap: 15px; margin-top: 10px; flex-wrap: wrap;">
                            <label style="flex: 1; min-width: 120px; background: rgba(30, 30, 40, 0.6); padding: 15px; cursor: pointer;">


get comments 
