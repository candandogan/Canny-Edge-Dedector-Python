# Canny-Edge-Dedector-Python
Bu projenin amacı, Python kullanarak Canny Kenar Tespit (Canny Edge Detector) algoritmasını yazmaktır. Önemli Not: Bu projede, OpenCV gibi görüntü işleme ve bilgisayarla görme kütüphanelerinin Canny Edge Detector yöntemleri kullanılmayacaktır. 
Canny kenar tespit algoritması süreci 6 farklı adımda incelenebilir:
1. Görüntünün gri (grayscale) görüntüye dönüşümü
2. Görüntüdeki gürültüleri gidermek için görüntüyü Gauss filtresi uygulayarak yumuşatmak 
Gauss filtresi ile görüntü yumuşatma, görüntüdeki gürültünün bir kısmını ortadan kaldırır. Çekirdek
(kernel) boyutunu ve sigma değerini deneme yanılma yoluyla belirleyebilirsiniz.
3. Görüntüde bir yönde oluşan ışık yoğunluğu değişimlerini (gradyanlarını) bulmak 
Gradyanlar hesaplanırken kenar yoğunluğu ve yönü göz önüne alınır. Gradyanlar, Sobel filtresi
kullanılarak belirlenebilir. Daha sonra, gradyanın büyüklüğü G ve eğimi θ aşağıdaki gibi hesaplanır (x
ve y için Ix ve Iy türevleri, görüntüye [Image (I)] x ve y yönlerinde Sobel filtresi uygulanarak
(convolution) hesaplanır.
4. Gereksiz kenarlardan kurtulmak için Non-Max Suppression uygulamak 
Sobel Edge ile elde edilen gereksiz / yinelenen kenarları kaldırmak için Non-Max Suppression uygulanır.
Aynı kenar için birden fazla çizgi yerine kenarların tek bir çizgi şeklinde gösterilmesi daha uygundur. Bu,
Non-Max Suppression algoritması ile sağlanabilir.
5. Olası kenarları belirlemek için çift eşik uygulamak. 
Zayıf gradyan değerine sahip kenar piksellerini filtrelemek ve yüksek gradyan değerine sahip kenar
piksellerini korumak için bir yüksek ve bir düşük eşik olmak üzere iki eşik ayarlanır.
6. Hysteresis ile kenarların korunması: Zayıf olan ve güçlü kenarlara bağlı olmayan diğer tüm
kenarlar elenir. 
