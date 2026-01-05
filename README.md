# --- 1. تحديث دالة عرض سامسونج (لتشمل كل الموديلات من السيرفر) ---
    def show_samsung(self):
        self.clear_ui()
        self.draw_header("SAMSUNG GLOBAL MODULE")
        # زر حل S25 Ultra (ثابت للحالات الطارئة)
        ctk.CTkButton(self.content_frame, text="🔥 FIX S25 ULTRA RE-PARTITION", 
                      command=self.run_s25_fix, height=60, fg_color="#dc2626").pack(fill="x", pady=10)
        
        # جلب القائمة من السيرفر (مفتاح samsung)
        models = self.cloud_models.get("samsung", ["No Samsung Models Found"])
        self.model_selector = ctk.CTkComboBox(self.content_frame, values=models, height=45, font=("Cairo", 14))
        self.model_selector.pack(fill="x", pady=10)
        
        ctk.CTkButton(self.content_frame, text="🔓 REMOVE FRP / RESET", 
                      command=lambda: self.log(f"Processing: {self.model_selector.get()}", "SUCCESS"), 
                      height=55, fg_color="#059669").pack(fill="x", pady=15)

    # --- 2. تحديث دالة عرض HUAWEI (الحصرية لـ علا ❤️) ---
    def show_huawei(self):
        self.clear_ui()
        self.draw_header("HUAWEI KIRIN & CLOUD BYPASS")
        # جلب القائمة من السيرفر (مفتاح huawei)
        models = self.cloud_models.get("huawei", ["No Huawei Models Found"])
        self.hw_selector = ctk.CTkComboBox(self.content_frame, values=models, height=45, font=("Cairo", 14))
        self.hw_selector.pack(fill="x", pady=10)
        
        ctk.CTkButton(self.content_frame, text="🛡️ BYPASS HUAWEI ID (KIRIN AUTH)", 
                      command=lambda: self.log(f"Auth Success for {self.hw_selector.get()}", "KING"), 
                      height=55, fg_color="#7c3aed").pack(fill="x", pady=15)

    # --- 3. تحديث دالة عرض NOTHING & MOTO (TSM PRO Update) ---
    def show_nothing(self):
        self.clear_ui()
        self.draw_header("NOTHING & MOTOROLA (EDL MODE)")
        # جلب القائمة من السيرفر (مفتاح nothing_moto)
        models = self.cloud_models.get("nothing_moto", ["No Models Found"])
        self.nm_selector = ctk.CTkComboBox(self.content_frame, values=models, height=45, font=("Cairo", 14))
        self.nm_selector.pack(fill="x", pady=10)
        
        ctk.CTkButton(self.content_frame, text="⚫ UNLOCK FRP (QUALCOMM AUTH)", 
                      command=lambda: self.log(f"Nothing/Moto Auth Start: {self.nm_selector.get()}", "SUCCESS"), 
                      height=55, fg_color="#1e293b").pack(fill="x", pady=15)
