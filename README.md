# TPMN-퍼블리셔 Tracker 통합 프로세스

### 1. TPMN으로부터 inventory ID를 발급 받으세요.

### 2. pointberry-event-tracker-v1.0.0.aar을 다운로드 하여 프로젝트에 추가하세요.

### 3. `PointBerryImpressionTracker` 객체를 다음과 같이 선언하세요.
~~~java
PointBerryImpressionTracker = pbImpTracker = new PointBerryImpressionTracker(getApplicationContext());
~~~

### 4. 광고 리스너의 impression 콜백에서 `logImpression()`을 호출하세요. 다음은 MoPub의 예시입니다.
#### `MoPubView.BannerAdListener`
~~~java
@Override
public void onBannerLoaded(MoPubView banner) {
    // The banner has successfully retrieved an ad.
    
    pbImpTracker.logImpression(YOUR_BANNER_INVENTORY_ID_HERE); // 발급 받은 배너 invertory ID를 넣으세요.
}
~~~
#### `MoPubInterstitial.InterstitialAdListener`
~~~java
@Override
public void onInterstitialShown(MoPubInterstitial interstitial) {
   // The interstitial has been shown.
   
   pbImpTracker.logImpression(YOUR_INTERSTITIAL_INVENTORY_ID_HERE); // 발급 받은 인터스티셜 invertory ID를 넣으세요.
}
~~~
