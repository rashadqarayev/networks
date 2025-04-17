## Lesson2

ARP (Address Resolution Protocol) 3-cü təbəqə (Şəbəkə Təbəqəsi) ünvanlarını 2-ci təbəqə (Məlumatların Verilməsi Təbəqəsi) ünvanlarına (MAC ünvanlarına) çevirmək üçün istifadə olunur.

Təsəvvür edək ki, iki kompüter (host) bir-biri ilə əlaqə qurmaq istəyir. 3-cü təbəqədə IP paketi enkapsulyasiya olunur və 2-ci təbəqəyə enir. Məlumatların Verilməsi Təbəqəsi başlıqını yaratmaq üçün mənbə və təyinat MAC ünvanlarına ehtiyac duyulur.

PC0 kompüteri PC1 kompüteri ilə əlaqə qurmaq istəyir. PC0 öz MAC ünvanını, IP ünvanını və təyinat IP ünvanını bilir. PC1-in MAC ünvanını öyrənmək üçün PC0 ARP protokolundan istifadə edir.

1.  PC0 öz ARP cədvəlində PC1 haqqında heç bir qeyd olmadığını görür (`>arp –a`).
2.  PC0 `FFFF.FFFF.FFFF` yayım MAC ünvanına bir ARP sorğusu göndərir: "192.168.1.2 kimdir?".
3.  PC1 öz IP ünvanını müəyyən edir və ARP cavab mesajı ilə cavab verir: "Mənəm! Və bu mənim MAC ünvanımdır".
4.  PC0 PC1-in MAC ünvanını öz ARP cədvəlinə əlavə edir.

`arp –d` komandasından istifadə edərək ARP cədvəlinin keşini təmizləyə bilərik.

## Lesson3

MAC ünvanı (Media Access Control address) şəbəkə interfeys kartlarına (NIC) istehsalçılar tərəfindən təyin edilir və 48 bit uzunluğundadır. MAC ünvanları CAM (Content Addressable Memory - Məzmun Ünvanlı Yaddaş) cədvəlində saxlanılır.

Digər istinad adları:

* Quraşdırılmış ünvan (Burned-in-address)
* Aparat təminatı ünvanı (Hardware address)
* Ethernet ünvanı

MAC ünvanı formatı: hər bir oktet 8 bitdir. MAC ünvanı iki hissədən ibarətdir:

* OUI (Organizationally Unique Identifier) - Təşkilati Unikal İdentifikator (ilk 24 bit). Bu hissə istehsalçını təyin edir.
* Vendor (İstehsalçı) - Cisco, Huawei, Alcatel, HP və s. (OUI bu istehsalçılara aiddir).
* İkinci hissə (son 24 bit) istehsalçı tərəfindən təyin edilən unikal cihaz identifikasiya nömrəsidir.

MAC ünvanının müxtəlif yazılış formaları:

* `0050.7966.6802`
* `00:50:79:66:68:02`
* `00-50-79-66-68-02`
* `0050-7966-6802`

Burada `oct1`, `oct2`, `oct3` və s. hər biri 8 bit olan oktetləri təmsil edir.

## Dərs 9: VLAN və VLAN Trunking

Bu dərsdə aşağıdakı mövzular əhatə olunur:

* **Broadcast Domain (Yayım Sahəsi):** LAN konsepsiyasında bütün switch portları standart olaraq VLAN 1-ə təyin olunur. Bu, standart VLAN adlanır. Bu səbəbdən, switch portlarına qoşulmuş bütün cihazlar eyni LAN-da olur və bütün cihazların eyni yayım sahəsində olduğu deyilir. Switch, qoşulmuş portlarından hər hansı birindən frame qəbul etdikdə, qəbul edən port istisna olmaqla, frame-i bütün portlarına ötürür. VLAN-lardan istifadə edərək çoxsaylı yayım sahəsi yarada bilərik. [cite: 3, 4, 5, 6, 7, 8]
* **VLAN Tərifi:** VLAN-dan istifadə edərək, bir yayım sahəsini kiçik yayım sahələrinə bölürük. Hər VLAN bir yayım sahəsidir. Hər VLAN-ın öz alt şəbəkəsi var. Məsələn, VLAN 1: 192.168.1.0/24, VLAN 2: 192.168.2.0/24. [cite: 7, 8, 9, 10, 11]
* **VLAN Konfiqurasiyası:** Topologiyaya uyğun olaraq switch portlarını konfiqurasiya edirik. Məsələn, PC2 və PC4 VLAN 10-da, PC3 və PC5 VLAN 20-də ola bilər. VLAN yaratmaq və portları VLAN-a təyin etmək üçün müxtəlif komandalar istifadə olunur (məsələn, `vlan 10`, `switchport access vlan 10`, `switchport mode access`). `switchport mode access` komandası standart olaraq switch portlarını access moduna təyin edir. [cite: 14, 15, 16]
* **VLAN Etiketləmə Konsepsiyası:** Eyni VLAN-da, lakin müxtəlif switchlərdə olan PC-lərin əlaqəsi üçün, switchlər arasında hər VLAN üçün fiziki bağlantıya ehtiyacımız var. Lakin bu miqyaslana bilən deyil. Bu problemin həlli VLAN etiketləməsidir. VLAN trunking, switchlər arasında çoxsaylı VLAN-ı dəstəkləyən bir bağlantı yaradır. VLAN trunk olaraq, switchlər bu bağlantını bütün VLAN-ların bir hissəsi kimi qəbul edirlər. Eyni zamanda, trunk VLAN trafikini ayrı saxlayır. [cite: 21, 22, 23, 24, 25, 26, 27]
* **VLAN Trunking Protokolları:** Switchlər, Ethernet frame-ə kiçik bir başlıq əlavə edərək, çoxsaylı VLAN-dan gələn frame-ləri tək bir fiziki bağlantı üzərindən ötürə bilirlər. Cisco, illər ərzində iki fərqli trunking protokolunu dəstəkləyib: ISL (Inter-Switch Link) və 802.1Q. Bu gün 802.1Q daha populyar trunking protokoludur. Hər iki protokol da hər frame-i VLAN ID ilə etiketləsə də, detallar fərqlidir. 802.1Q orijinal frame-in Ethernet başlığına əlavə 4 baytlıq 802.1Q VLAN başlığı əlavə edir. 802.1Q başlığı = 32 bit, VLAN ID = 12 bit. [cite: 29, 30, 31, 32, 33, 34, 35, 36, 37, 38]
* **VLAN Trunking Konfiqurasiyası:** Trunk portunu interfeys konfiqurasiya rejimində `switchport mode trunk` komandasından istifadə edərək statik olaraq konfiqurasiya edə bilərik. Cisco switchlərində trunking konfiqurasiyası, müxtəlif trunking parametrlərini dinamik olaraq müzakirə etmək üçün bir neçə seçim daxil olmaqla, daha çox seçimi əhatə edir. Konfiqurasiya müxtəlif parametrləri əvvəlcədən təyin edə və ya switch-ə parametrləri müzakirə etməsini söyləyə bilər. Müzakirə DTP (Dynamic Trunking Protocol) tərəfindən aparılır. `switchport mode trunk` komandası bütün VLAN-ların trunk portundan keçməsinə icazə verir. Xüsusi VLAN-lara icazə veririksə, `switchport trunk allow vlan 10,20,30` komandasından istifadə edirik. Native VLAN-ı da dəyişə bilərik. Standart olaraq native VLAN 1-dir (standart VLAN). `switchport trunk native vlan 10` komandası ilə dəyişirik. [cite: 39, 40, 41, 42, 43, 44, 45]
* **Switch Portlarının İşləmə Rejimləri:** Bu mövzu ayrıca qeyd olunur. [cite: 46]


**Dərs 11: Spanning-Tree Protokolu (STP)**

Bu dərsdə Spanning-Tree Protokolu (STP) və onun əsasları, işləmə prinsipi və switchlərdə konfiqurasiyası haqqında məlumat verilir.

* **STP & RSTP Əsasları:** STP və ya RSTP olmadan, bir Ethernet frame LAN-da qeyri-müəyyən müddətə dövr edəcəkdir[cite: 9]. STP və ya RSTP aktiv olduqda, Ethernet switchi bəzi switch portlarını bloklayacaq və bu portlar frame ötürməyəcək və 2-ci təbəqə döngələrindən xilas olacaqdır[cite: 10]. Üç switchdən ibarət topologiyamız var: STP/RSTP olmadan switchlər frame-ləri ötürmə məntiqinə uyğun olaraq ötürəcəklər[cite: 11]. Nəticədə, yayım fırtınası yaranacaq[cite: 12].
* **STP-nin Funksiyası Nədir?** STP/RSTP, hər bir switch portunu ötürmə və ya bloklama vəziyyətinə qoyaraq döngülərin qarşısını alır[cite: 19]. Ötürmə vəziyyətində olan interfeyslər normal işləyir, frame-ləri ötürür və qəbul edirlər[cite: 20]. Lakin, bloklama vəziyyətində olan interfeyslər STP/RSTP mesajları (və bəzi digər overhead mesajları) istisna olmaqla, heç bir frame-i emal etmir[cite: 21, 22].
* **STP Necə İşləyir?** Spanning-tree, interfeysləri ötürmə və ya bloklama vəziyyətinə qoymaq üçün interfeysləri seçən Spanning Tree Alqoritmindən (STA) istifadə edir[cite: 27]. STP Ethernet LAN seqmentində root-bridge (master-switch) seçir. STP/RSTP, switchlərin bir-biri ilə məlumat mübadiləsi aparmaq üçün istifadə etdiyi bridge protocol data units (BPDU) adlanan mesajları təyin edir[cite: 28, 29, 30, 31, 32].
* **Root-Bridge Seçim Prosesi:** Switchlər, BPDU-dakı BID-lərə əsasən root switchi seçirlər[cite: 33, 34]. Root switch, BID üçün ən aşağı ədədi dəyərə sahib olan switchdir[cite: 35]. BID-in iki hissəsi priority dəyəri ilə başladığı üçün, mahiyyət etibarilə ən aşağı priority-ə sahib olan switch root olur[cite: 36, 37, 38, 39, 40, 41].
* **Root Portun Seçilməsi:** STP/RSTP prosesinin ikinci hissəsi, hər bir qeyri-root switchin özünün tək və yeganə root portunu seçdiyi zaman baş verir[cite: 45, 46, 47, 48, 49, 50].
* **Təyin Edilmiş Portun Seçilməsi:** STP/RSTP topologiyasını seçmək üçün STP/RSTP-nin son addımı, hər bir LAN seqmentində təyin edilmiş portu seçməkdir[cite: 51, 52, 53, 54, 55].
* **Xüsusi Qaydalar:** Bütün Root Switch-lərin interfeysləri Təyin Edilmiş Portlardır və ötürmə vəziyyətindədirlər[cite: 56, 57].
* **Praktiki Baxış:** Topologiyada üç switchimiz var: #show spanning-tree komandasından istifadə edərək mövcud spanning-tree vəziyyətini təhlil edirik[cite: 58, 59].

Dərsin sonunda müəllif öyrənməyin, təkrarlamağın və təcrübə etməyin vacibliyini vurğulayır[cite: 60].
