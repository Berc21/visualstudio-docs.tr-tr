---
title: "3. adım: geri sayım Zamanlayıcısı ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62670a2b-efdc-45c6-9646-9b17eeb33dcb
caps.latest.revision: "23"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 09d956f897e81d5e785c561a69cc8b716375676d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="step-3-add-a-countdown-timer"></a>3. Adım: Geri Sayım Zamanlayıcısı Ekleme
Bu öğreticinin üçüncü bölümünde test alanın tamamlamak kalan saniye sayısını izlemek için geri sayım Zamanlayıcısı ekleyeceksiniz.  
  
> [!NOTE]
>  Bu konuda bir öğretici serisi kodlama temel kavramları hakkında bir parçasıdır. Öğretici genel bakış için bkz: [Eğitmen 2: bir zaman aşımına matematik test oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md).  
  
### <a name="to-add-a-countdown-timer"></a>Bir geri sayım Zamanlayıcısı ekleme  
  
1.  Adlı bir tamsayı değişken Ekle **timeLeft**, önceki yordamda yaptığınız gibi. Kodunuzu aşağıdaki gibi görünmelidir.  
  
     [!code-vb[VbExpressTutorial3Step3#5](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_1.vb)]
     [!code-csharp[VbExpressTutorial3Step3#5](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_1.cs)]  
  
     Şimdi gerçekte, belirttiğiniz süre miktarını sonra bir olay başlatır bir süreölçer gibi saniye sayısı bir yöntem gerekir.  
  
2.  Tasarım penceresinde taşımak bir `Timer` gelen denetim **bileşenleri** formunuza araç kategorisi.  
  
     Tasarım pencerenin altındaki gri alanında denetimi görünür.  
  
3.  Form üzerinde seçin **Süreölçer1** yalnızca eklenen ve ayarlama simgesi kendi **aralığı** özelliğine **1000**.  
  
     Aralık değeri milisaniye olduğundan, 1000 değerini saniyede tetiklenecek onay olay neden olur.  
  
4.  Form üzerinde Zamanlayıcı denetimi çift tıklatın veya onu seçin ve ardından Enter tuşuna seçin.  
  
     Kod Düzenleyicisi görünür ve eklediğiniz onay olay işleyicisi için yöntemini görüntüler.  
  
5.  Yeni bir olay işleyicisi yöntemi aşağıdaki deyimleri ekleyin.  
  
     [!code-vb[VbExpressTutorial3Step3#6](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_2.vb)]
     [!code-csharp[VbExpressTutorial3Step3#6](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_2.cs)]  
  
     Belirleyerek zaman bitti olup olmadığını, eklediğiniz üzerinde bağlı olarak, Zamanlayıcı saniyede denetler olup olmadığını **timeLeft** 0'dan büyük tamsayı değişken. Saat ise, hala kalır. Zamanlayıcı ilk timeLeft 1 çıkarır ve ardından güncelleştirmeleri **metin** özelliği `timeLabel` kaç saniye kaldı test alanın göstermek için denetim.  
  
     Hiçbir zaman kalırsa, Zamanlayıcı durdurur ve metnini değiştirir `timeLabel` gösterir, böylece denetim **zaman yukarı!** Test bittiğinde ve yanıt ortaya bir ileti kutusu sunar — bu durumda, ekleyerek addend1 ve addend2. **Etkin** özelliği `startButton` denetim ayarlanmış `true` test alanın başka bir test başlatabilirsiniz.  
  
     Yeni eklediğiniz bir `if else` kararlar almak için programlar nasıl çalıştığını bildiren olan ifade. Bir `if else` deyimi aşağıdaki gibi görünür.  
  
    > [!NOTE]
    >  Aşağıdaki örnekte yalnızca gösterim amacıyla olduğu-projenize eklemeyin.  
  
    ```vb  
    If (something that your program will check) Then  
        ' One or more statements that will run  
        ' if what the program checked is true.   
    Else  
        ' One or more statements that will run  
        ' if what the program checked is false.  
    End If  
    ```  
  
    ```csharp  
    if (something that your program will check)  
    {  
        // One or more statements that will run  
        // if what the program checked is true.   
    }  
    else  
    {  
        // One or more statements that will run  
        // if what the program checked is false.  
    }  
    ```  
  
     Bakabilir yakından eklediğiniz deyimi `else` toplama problemi yanıtı göstermek için blok.  
  
     [!code-vb[VbExpressTutorial3Step3#24](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_3.vb)]
     [!code-csharp[VbExpressTutorial3Step3#24](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_3.cs)]  
  
     Deyim `addend1 + addend2` iki değişken değerleri toplar. İlk bölümü (`sum.Value`) kullanan **değeri** özelliği Sum `NumericUpDown` doğru yanıt görüntülemek için denetimi. Aynı özelliği daha sonra test için yanıtları denetlemek için kullanın.  
  
     Test tutmayı girebilirsiniz numaralarını daha kolay kullanarak bir `NumericUpDown` matematik sorunlara yanıtlar için kullandığınız neden olan denetim. Olası yanıtlar tam sayılar 0 ile 100 arasında tümü. Varsayılan değerleri bırakarak **Minimum**, **maksimum**, ve **ondalık basamaklar** özellikleri, emin test tutmayı gönderilemiyor ondalık girin, negatif sayıları, veya çok yüksek sayılar. (Test tutmayı 3,141 girmek izin istedi, ancak değil 3.1415, ayarlayabilirsiniz **ondalık basamaklar** özelliği 3.)  
  
6.  Üç satır sonuna ekleyin `StartTheQuiz()` yöntemi kodu aşağıdaki gibi görünür.  
  
     [!code-vb[VbExpressTutorial3Step3#7](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_4.vb)]
     [!code-csharp[VbExpressTutorial3Step3#7](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_4.cs)]  
  
     Şimdi, test başladığında, **timeLeft** değişkenini 30 ve **metin** özelliği `timeLabel` denetim 30 saniyeye ayarlayın. Ardından `Start()` yöntemi `Timer` denetimi geri sayım başlatır. (Test yanıt henüz denetlemez — sonraki gelen.)  
  
7.  Programınızı kaydetmek, çalıştırın ve ardından **Başlat** formundaki düğmesi.  
  
     Sayılacak süreölçer başlatır. Ne zaman çıkış test uçları çalıştığında ve yanıt görünür. Aşağıdaki çizimde test göstermektedir.  
  
     ![Devam eden matematik testi](../ide/media/express_addcountdown.png "Express_AddCountdown")  
Matematik testi sürüyor  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [4. adım: CheckTheAnswer() yöntemi ekleme](../ide/step-4-add-the-checktheanswer-parens-method.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [2. adım: rasgele bir toplama problemi oluşturma](../ide/step-2-create-a-random-addition-problem.md).