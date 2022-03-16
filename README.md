# Face_Mask_Detection

## PROJENİN AMACI

Bu projenin amacı, yapay zeka teknikleri kullanılarak kameradan gelen görüntüdeki insanın yüzünde maske olup olmadığını tespit eden sistemi geliştirmektir.

## PROJENİN ÖZETİ

Bu proje temel olarak iki kısımdan oluşmaktadır. İlk kısımda Kaggle'dan alınmış yaklaşık 3800 maskesiz ve 3725 maskeli yüz resmine sahip bir veri seti, kişinin yüzünde maske olup olmadığını sınıflandıracak bir derin öğrenme modelini beslemek için kullanılmıştır. Bu model projenin ikinci kısmında kullanılmak üzere kaydedilmiştir. İkinci kısımda ise bir kamera kaydı başlatılarak görüntüdeki kişinin yüzünün konumunun anlık olarak tespit edilmesi daha sonrasında bu konum bilgileri kullanılarak alınan görüntü ile kişinin yüzünde maske olup olmadığı tespit edilmesi sağlanmıştır.

## Kaynak kodu: 

## PROJEDE KULLANILAN TEKNOLOJİLER

### Kullanılan Programlar: Jupyter Notebook

### Kullanılan Programlama Dilleri: Python

## Kullanılan Kütüphaneler:

face_recognation: Yüz tanıma işlemini basitleştirmek için geliştirilmiş bir python kütüphanesi.

Keras: Neredeyse her tür derin öğrenme modelini tanımlamak ve eğitmek için uygun bir yol sağlayan Python için bir derin öğrenme kütüphanesidir. Keras, Tensorflow , Theano ve CNTK üzerinde çalışabilen Python ile yazılmış bir üst düzey sinir ağları API'sıdır.

OpenCV: OpenCV (Open Source Computer Vision) açık kaynak kodlu görüntü işleme kütüphanesidir.

NumPy: Python programlama dili için büyük, çok boyutlu dizileri ve matrisleri destekleyen, bu diziler üzerinde çalışacak üst düzey matematiksel işlevler ekleyen bir kitaplıktır.


# PROJE YAPIM AŞAMALARI

## PART 1: 

### STEP 1 
Dataset %80 train, %20 test olarak tanımlanır, sınıflar tespit edilir. Preprocessing işlemi gerçekleştirilir.

![1](https://user-images.githubusercontent.com/78687240/158424292-2d1d6d98-e19f-41f9-aab1-cc5da59bac92.png)

### STEP 2 
Kullandığımız model, Evrişimli Sinir Ağları (CNN) kullanılarak Keras ile oluşturulmuştur. Bir evrişimli sinir ağı, görüntü sınıflandırma amaçları için son derece iyi performans gösteren özel bir derin sinir ağı türüdür. Bir CNN temel olarak bir girdi katmanı, bir çıktı katmanı ve birden çok katmana sahip olabilen bir gizli katmandan oluşur. Katman ve filtre üzerinde 2B matris çarpımı gerçekleştiren bir filtre kullanılarak bu katmanlar üzerinde bir evrişim işlemi gerçekleştirilir. CNN model mimarisi aşağıdaki katmanlardan oluşur:

Evrişimsel katman; 32 düğüm, çekirdek boyutu 4

Evrişimsel katman; 32 düğüm, çekirdek boyutu 4

Evrişimsel katman; 32 düğüm, çekirdek boyutu 4

Tam bağlantılı katman; 128 düğüm

Son katman ayrıca 1 düğümlü tam bağlantılı bir katmandır. Sigmoid kullandığımız çıktı katmanı dışındaki tüm katmanlarda bir Relu aktivasyon işlevi kullanılır.
![3](https://user-images.githubusercontent.com/78687240/158425193-24ee28b6-5f45-4f24-a229-bba52c3cdab6.png)

## PART 2:

### STEP 1
Görüntüdeki yüzlerin konumunun belirlenebilmesi için OpenCV tarafından daha önceden hazırlanmış XML dosyası (Face Cascade) tanımlanır ve Part 1'de eğitilen model yüklenir.  
![5](https://user-images.githubusercontent.com/78687240/158425550-3e7ceaaf-36d0-44cd-92f7-3edb03217cef.png)

### Step 2
Kamera açılır; kameradaki kişinin yüzünün konumu cascade classifier ile belirlenir, daha iyi bir tahmin için konum bilgisiyle görüntüdeki kişinin yüzü kırpılarak resim haline getirilir. Preprocessing işleminden sonra model ile tahmin yapılır.
![7](https://user-images.githubusercontent.com/78687240/158566726-509cb6a2-17eb-415a-975b-57d0eca8526f.png)
