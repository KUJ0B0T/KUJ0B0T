<div align='center'>
  <img src="https://capsule-render.vercel.app/api?type=waving&fontColor=48648a&height=150&section=header&text=PEN%20CRAFT&fontSize=40&desc=Smart%20Factory&descAlignY=70&descAlign=50"/>
  <h3>🖍보드마카 생산 공장🖍</h3>
  <h4>☑ 제품별 품질 관리</h4>
  <h4>☑ 라인 내 에러 정보 통합 모니터링</h4>
  <h4>☑ 분석 시스템 구축</h4>
</div>

## 📞0. 목차
1. [프로젝트 소개](#1)
2. [개발 일정](#2)
3. [개발 환경 / Dependencies / 기술 스택](#3)
4. [프로젝트 폴더 구조](#4)
5. [주요 기능 소개](#5)
6. [핵심 코드](#6)
7. [트러블 슈팅](#7)
8. [리팩토링 필요](#8)
9. [리팩토링 완료](#9)
10. [느낀 점 및 아쉬운 점](#10)
<br><br><br><br>
<span id="1"></span>
## 🏭1. 프로젝트 소개
해당 프로젝트는 5명의 인원으로 제품별 품질 관리와 라인 내 에러 정보 통합 모니터링 및 분석 시스템 구축이라는 스마트 팩토리의 주제를 선정하였을 때 실제 공장에서 일을 해본 적 경험이 없는 저희로서는 생각했을 때 직관적이고 단순하게 생각할 수 있는 보드마카를 생산하는 공장을 선정하였습니다.
저희의 프로젝트에서는 제품을 생산하는 4가지의 공정이 있고, 생산 지시가 내려졌을 때 1공정부터 4공정까지 진행이 되었을 때 각 공정마다 일정 시간이 지난 뒤 그래프를 통해 양품과 불량품의 개수가 보일 수 있도록 모니터링을 할 수 있게 하고 생산된 제품들은 품질 관리 페이지에서 제품별 품질 관리를 할 수 있는 기능을 가지고 있습니다. 생산되는 현황을 확인하고 생산된 제품의 품질을 관리할 수 있는 PEN CRAFT 프로젝트의 완성 과정을 소개해드리겠습니다.
<br><br><br><br>
<span id="2"></span>
## 📆2. 개발 일정
#### [2024.02.19 ~ 2024.03.15]
2024.02.19 ~ 2024.02.26 : 기획
2024.02.25 ~ 2024.03.10 : UI 및 기능 구현
2024.03.11 ~ 2024.03.15 : 테스트 및 리팩토링
<br><br><br><br>

<span id="3"></span>
## ⚙3. 개발 환경 / Dependencies / 기술 스택
### 🛠개발환경
  - **OS : Windows 10**
  - **통합개발환경(IDE) : IntelliJ**
  - **JDK Version : JDK 17**
  - **Database : MySQL**
  - **Build Tool : IntelliJ IDEA**

### 🖥Dependencies
  - **Spring Web**
  - **Spring Data JPA**
  - **Spring Boot DevTools**
  - **WebSocket**
  - **Lombok**
  - **Mysql Driver**
  - **Thymeleaf**

### ✏기술 스택
  - **Front End**<br>
![HTML](https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)
![Javascript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=white)
![jQuery](https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-239120?style=for-the-badge)
  - **Back End**<br>
![Spring](https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-red?style=for-the-badge)
![JPA](https://img.shields.io/badge/JPA-DB7093?style=for-the-badge)
  - **Database**<br>
![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white)
![Woekbench](https://img.shields.io/badge/MySQL%20Workbench-00000F?style=for-the-badge&logo=mysql&logoColor=white)
  - **Communication**<br>
![Notion](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white)
![Discord](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)
<br><br><br><br>

<span id="4"></span>
## 🗂4. 프로젝트 폴더 구조
```
📁src
┣ 📂main
┃ ┣ 📂java
┃ ┃ ┣ 📂com.example.pencraft
┃ ┃ ┃ ┣ 📂config
┃ ┃ ┃ ┃ ┣ 📄WebConfig.java
┃ ┃ ┃ ┃ ┗ 📄WebSocketConfig.java
┃ ┃ ┃ ┣ 📂constant
┃ ┃ ┃ ┃ ┗ 📄SessionConst.java
┃ ┃ ┃ ┣ 📂controller
┃ ┃ ┃ ┃ ┣ 📄EmployeeController.java
┃ ┃ ┃ ┃ ┣ 📄HomeController.java
┃ ┃ ┃ ┃ ┣ 📄LoginController.java
┃ ┃ ┃ ┃ ┣ 📄ProcessController.java
┃ ┃ ┃ ┃ ┗ 📄ProductController.java
┃ ┃ ┃ ┣ 📂domain
┃ ┃ ┃ ┃ ┣ 📄BaseTimeEntity.java
┃ ┃ ┃ ┃ ┣ 📄Employees.java
┃ ┃ ┃ ┃ ┣ 📄Error.java
┃ ┃ ┃ ┃ ┣ 📄Lot.java
┃ ┃ ┃ ┃ ┣ 📄OccurrenceError.java
┃ ┃ ┃ ┃ ┣ 📄Process.java
┃ ┃ ┃ ┃ ┣ 📄Product.java
┃ ┃ ┃ ┃ ┗ 📄Standard.java
┃ ┃ ┃ ┣ 📂filter
┃ ┃ ┃ ┃ ┣ 📄LogFilter.java
┃ ┃ ┃ ┃ ┗ 📄LoginCheckFilter.java
┃ ┃ ┃ ┣ 📂form
┃ ┃ ┃ ┃ ┣ 📄CountForm.java
┃ ┃ ┃ ┃ ┣ 📄EmployeesForm.java
┃ ┃ ┃ ┃ ┣ 📄LoginForm.java
┃ ┃ ┃ ┃ ┣ 📄LotForm.java
┃ ┃ ┃ ┃ ┗ 📄ProductForm.java
┃ ┃ ┃ ┣ 📂repository
┃ ┃ ┃ ┃ ┣ 📄EmployeesRepository.java
┃ ┃ ┃ ┃ ┣ 📄LotRepository.java
┃ ┃ ┃ ┃ ┣ 📄ProcessRepository.java
┃ ┃ ┃ ┃ ┣ 📄ProductRepository.java
┃ ┃ ┃ ┃ ┗ 📄StandardRepository.java
┃ ┃ ┃ ┗ 📂service
┃ ┃ ┃ ┃ ┣ 📄EmployeesService.java
┃ ┃ ┃ ┃ ┣ 📄LoginService.java
┃ ┃ ┃ ┃ ┣ 📄LotService.java
┃ ┃ ┃ ┃ ┣ 📄ProcessService.java
┃ ┃ ┃ ┃ ┣ 📄ProductService.java
┃ ┃ ┃ ┃ ┗ 📄WebSocketSenderService.java
┃ ┃ ┃ ┗ 📄PencraftApplication.java
┃ ┗ 📂resource
┃ ┃ ┣ 📂static
┃ ┃ ┃ ┣ 📂css
┃ ┃ ┃ ┃ ┣ 📄bootstrap.css
┃ ┃ ┃ ┃ ┣ 📄jumbotron-narrow.css
┃ ┃ ┃ ┃ ┗ 📄style.css
┃ ┃ ┃ ┣ 📂img
┃ ┃ ┃ ┗ 📂js
┃ ┃ ┃ ┃ ┣ 📄bootstrap.bundle.min.js
┃ ┃ ┃ ┃ ┗ 📄sock.js
┃ ┃ ┣ 📂templates
┃ ┃ ┃ ┣ 📂employees
┃ ┃ ┃ ┃ ┗ 📄createEmployeesForm.html
┃ ┃ ┃ ┣ 📂fragment
┃ ┃ ┃ ┃ ┣ 📄bodyheader.html
┃ ┃ ┃ ┃ ┗ 📄header.html
┃ ┃ ┃ ┣ 📂login
┃ ┃ ┃ ┃ ┗ 📄loginForm.html
┃ ┃ ┃ ┣ 📂products
┃ ┃ ┃ ┃ ┣ 📄monitoring.html
┃ ┃ ┃ ┃ ┣ 📄showProducts.html
┃ ┃ ┃ ┃ ┗ 📄start_process.html
┃ ┃ ┃ ┣ 📄home.html
┃ ┃ ┃ ┣ 📄loginAdminHome.html
┗ ━ ━ ┷ 📄loginStaffHome.html
```
<br><br><br><br>

<span id="5"></span>
## 🔍5. 주요 기능 소개
<br><br><br><br>

<span id="6"></span>
## ⌨6. 핵심 코드
<details>
  <summary><b>1공정 ~ 4공정 생산 로직</b></summary>
  반복문을 이용하여 제품을 생산하면서 N초 주기로 웹 소켓을 통해 클라이언트에게 데이터를 보내야하기 때문에 2개의 Thread가 필요<br>
  쓰레드의 관리가 편리한 ExecutorService를 이용하여 2개의 쓰레드 풀을 만들어 '생산'과 '데이터 전송'을 동시에 진행
  <br><br>
  1공정 : 하나의 Lot에서 N개의 제품을 생성하기 때문에 Lot의 생성과 N개의 제품을 리스트에 담아 랜덤한 잉크를 주입하고 제품 규격과 비교하여 양품과 불량품을 리스트에 저장<br>
  1공정이 종료된 후 2공정 메서드 실행
  <br><br>
  2공정 : 1공정에서 생산된 제품 중 양품인 제품만 닙(보드마카의 촉)을 삽입을 하는데 랜덤하게 닙 깊이를 삽입하여 제품 규격과 비교하여 불량품일 경우 양품&불량품 여부의 값을 불량으로 변경<br>
  2공정이 종료된 후 3공정 메서드 실행
  <br><br>
  3공정 : 2공정에서 생산된 제품 중 양품인 제품만 몸체를 결합하는데 랜덤하게 결합 여부를 Y, N으로 하여 불량일 경우 양품&불량품 여부의 값을 불량으로 변경<br>
  3공정이 종료된 후 4공정 메서드 실행
  <br><br>
  4공정 : 3공정에서 생단된 제품 중 양품인 제품만 뚜껑을 결합하는데 3공정과 동일하게 랜덤으로하여 불량품일 경우 양품&불량품 여부의 값을 불량으로 변경<br>
  4공정이 종료된 후 생산된 제품과 Lot을 데이터 베이스에 저장하는 메서드 실행
  
```java
      private final LotService lotService;
      private final ProductRepository productRepository;
      private final WebSocketSenderService webSocketSenderService;
      private Standard standard; // DB에서 가져온 규격을 저장
      private Lot lot; // Lot Entity
      private List<Product> productList; // 생산된 제품을 저장할 리스트
  
      private final ExecutorService executorService = Executors.newFixedThreadPool(2); // 쓰레드 개수 2개
      private Future<?> sendFuture; // 지속적으로 사용자에게 데이터를 보낼 Future
      private Future<?> productionFuture; // 생산을 담당할 Future
  
      // 사용자에게 양품, 불량품을 보내주기 위한 변수
      // 각 공정마다 최초 시작에 두 변수를 0으로 초기화해서 사용
      private int good_count;
      private int bad_count;
  
      private final int sendMessageDelay = 100; // 몇초 주기로 클라이언트에게 메세지를 보낼지 시간 설정
      private final int productionDelay = 10; // 제품 1개 생산하는데 몇 초마다 생산할지 시간 설정
  
      // 1공정 시작
      public void processFirst(CountForm countForm) throws Exception {
          log.info("생산량 ={}", countForm.getCount());
          standard = standardRepository.findById(1L).orElse(null);
          log.info("1공정 규격 = {}", standard);
          lot = new Lot();
          lot.setLot_id(1L);
          if(!lotRepository.findAll().isEmpty()) {
              lot.setLot_id(lotRepository.selectMaxLotId()+1);
          }
  
          lot.setOutput(countForm.getCount());
          lot.setStart_time(LocalDateTime.now()); // 생산 시작 시간을 현재 시간으로 저장
          lot.setFirst_start(LocalDateTime.now()); // 1공정 시작 시간을 현재 시간으로 저장
          lot.setStatus((char)49); // 상태를 진행 중(1)로 변경
          log.info("신규 생성될 Lot = {}", lot);
  
          productList = new ArrayList<>();
  
          productionFuture = executorService.submit(firstTask(countForm.getCount()));
          sendFuture = executorService.submit(sendMessage("/process/first"));
      }
  
      // 2 공정 시작
      private void processSecond() throws Exception {
          // lot에 2공정 시작 시간 추가
          lot.setSecond_start(LocalDateTime.now());
          productionFuture = executorService.submit(secondTask());
          sendFuture = executorService.submit(sendMessage("/process/second"));
      }
  
      private void processThird() throws Exception {
          // lot에 3공정 시작 시간 추가
          lot.setThird_start(LocalDateTime.now());
          productionFuture = executorService.submit(thirdTask());
          sendFuture = executorService.submit(sendMessage("/process/third"));
      }
  
      private void processFourth() throws Exception {
          // lot에 4공정 시작 시간 추가
          lot.setFourth_start(LocalDateTime.now());
          productionFuture = executorService.submit(fourthTask());
          sendFuture = executorService.submit(sendMessage("/process/fourth"));
      }
  
      private void saveAll() throws Exception {
          // 완성된 Lot Entity를 lotRepository를 통해 저장
          log.info("4공정까지 끝난 뒤 최종 제품 리스트 = {}", productList);
          log.info("4공정까지 끝난 뒤 최종 LOT 정보 = {}", lot);
  
          Lot checkLot = lotRepository.save(lot);
          log.info("DB에 저장한 뒤 반환 Lot = {}", checkLot);
  
          //생산된 제품들에게 로트번호&규격 부여
  
          for (Product product : productList) {
              product.setLot(lot);
              product.setStandard(standard);
          }
          // 생산된 모든 제품들을 productRespository를 통해 저장
          List<Product> chechkProductList = productRepository.saveAll(productList);
  
          log.info("DB에 저장한 뒤 반환 제품 리스트 = {}", chechkProductList);
      }
  
      // 생산 중단 메서드
      public void stopProduction() {
          // 생산과 메세지를 중단
          productionFuture.cancel(true);
          stopSend();
      }
  
      // 메세지 전송 중단 메서드
      private void stopSend() {
          sendFuture.cancel(true);
      }
  
      // 목적지(destination)으로 메세지를 무한 전송
      private Runnable sendMessage(String destination) {
          return () -> {
              while(true) { // 생산이 언제 끝날지 모르기에 무한 루프
                  // Map에 데이터(양품과 불량품의 수량)를 담아 클라이언트에게 전송
                  Map<String, Integer> data = new HashMap<>();
                  try {
                      if (Thread.currentThread().isInterrupted()) {
  //                        webSocketSenderService.sendMessageToClient("생산이 중단되었습니다.");
                          break;
                      }
                      Thread.sleep(sendMessageDelay); // N초 주기로
                      // 각 공정마다의 양품, 불량품을 Map에 넣어서 클라이언트에게 전송
                      data.put("goodcount", good_count);
                      data.put("badcount", bad_count);
                      webSocketSenderService.sendMessageToClient(destination,data);
                  } catch (InterruptedException e) {
                      log.error("Thread interrupted = ", e);
                      Thread.currentThread().interrupt(); // Preserve interrupted status
                  }
              }
          };
      }
  
      // 1공정 생산 로직
      private Runnable firstTask(int count){
          return () -> {
              good_count = 0;
              bad_count = 0;
              for (int i = 0; i < count; i++) {
                  try {
                      Thread.sleep(productionDelay); // N초마다 생성
                  } catch (InterruptedException e) {
                      throw new RuntimeException(e);
                  }
                  Random random = new Random();
                  // 랜덤의 시작과 끝을 설정할 변수
                  Double start = 0.0;
                  Double end = 0.0;
                  Double volume = 0.0;
                  int ran = random.nextInt(1, 101);
                  if(ran > 5) { // 양품
                      // 양품일 경우에는 98~102ml
                      start = 98.0; end = 102.0;
                  } else { // 불량
                      // 불량품은 90~98ml, 103 ~ 111ml로
                      // boolean의 값이 true일 경우 90~98ml
                      // boolean의 값이 false일 경우 103~111ml
                      boolean bool = random.nextBoolean();
                      if(bool){
                          start = 90.0; end = 98.0;
                      } else{
                          start = 103.0; end = 111.0;
                      }
                  }
                  // 시작 ~ 끝 값으로 랜덤한 double 값 추출
                  // 소수점 둘째자리 이하는 반올림하여 버리는 코드
                  volume = Math.round(random.nextDouble(start,end) * 100) / 100.0;
  
                  // 제품 Entity 생성
                  Product p = new Product();
                  // 위에서 만들어진 잉크량을 저장
                  p.setVolume(volume);
  
                  // 만약 잉크량이 제품 규격에 맞다면
                  if(standard.getMin_volume() <= volume && standard.getMax_volume() >= volume){
                      p.setAcceptance((char)49); // 양품 불량품 여부를 1(양품)로 설정
                      good_count++; // 양품의 개수를 1개 증가
                  }
                  else { // 만약 잉크량이 제품 규격에 맞지 않다면
                      p.setAcceptance((char)48); // 양품 불량품 여부를 0(불량품)으로 설정
                      bad_count++; // 불량품의 개수를 1개 증가
                  }
                  productList.add(p); // 제품 Entity를 리스트에 추가
                  log.info("productList = " + productList);
              }
              /*
                  여기 이후는 for문(생산)이 종료된 이후에 순차적으로 코드 실행
              * */
              lot.setFirst_end(LocalDateTime.now()); // 1공정 종료 시간에 현재 시간을 추가
              try {
                  /*
                      5초 대기
                      생산 로직이 종료되자마자 stopSend(); 메서드를 호출하여 sendFuture를 종료시킬 경우
                      시간의 아다리가 맞지 않으면 최종 양품(good_count)와 불량품(bad_count)의 개수가 클라이언트에게 가지 않음
                      Ex)
                      생산 지시 30개 -> 클라이언트가 받은 데이터 { 양품 : 22, 불량품 : 2 }
                      -> stopSend()가 실행되어 클라이언트는 더 이상 데이터를 받지 못함
                      그리하여, 메세지를 N초주기로 보내주기 때문에 sendMessageDelay초를 대기한 후
                      메세지를 더 이상 보내지 않도록 stopSend()메서드를 실행
                  */
                  Thread.sleep(sendMessageDelay);
              } catch (InterruptedException e) {
                  throw new RuntimeException(e);
              }
              stopSend();
              try {
                  processSecond();
              } catch (Exception e) {
                  throw new RuntimeException(e);
              }
          };
      }
  
      private Runnable secondTask(){
          return () -> {
              good_count = 0;
              bad_count = 0;
  
              for (int i = 0; i < productList.size(); i++) {
                  if(productList.get(i).getAcceptance()==48) // 만약 불량품이라면 패스
                      continue;
                  try {
                      Thread.sleep(productionDelay);
                  } catch (InterruptedException e) {
                      throw new RuntimeException(e);
                  }
                  Random random = new Random();
                  // 랜덤의 시작과 끝을 설정할 변수
                  Double start = 0.0;
                  Double end = 0.0;
                  Double nib = 0.0;
                  int ran = random.nextInt(1, 101);
                  if(ran > 5) { // 양품
                      // 양품일 경우에는 0.87~1.00
                      start = 0.87; end = 1.00;
                  } else { // 불량
                      // 불량품은 0.8 ~ 0.86, 1.01 ~ 1.05
                      // boolean의 값이 true일 경우 0.8 ~ 0.86
                      // boolean의 값이 false일 경우 1.01 ~ 1.05
                      boolean bool = random.nextBoolean();
                      if(bool){
                          start = 0.8; end = 0.865;
                      } else{
                          start = 1.005; end = 1.05;
                      }
                  }
                  // 시작 ~ 끝 값으로 랜덤한 double 값 추출
                  // 소수점 둘째자리 이하는 반올림하여 버리는 코드
                  nib = Math.round(random.nextDouble(start,end) * 100) / 100.0;
  
                  // productionList의 i번째 방에 있는 Product를 꺼내어 p에 저장
                  Product p = productList.get(i);
                  // 위에서 만들어진 닙의 깊이를 저장
                  p.setNib(nib);
  
                  // 만약 닙의 깊이가 제품 규격에 맞다면
                  if(standard.getMin_nib() <= nib && standard.getMax_nib() >= nib){
                      good_count++; // 양품의 개수를 1개 증가
                  }
                  else { // 만약 닙의 깊이가 제품 규격에 맞지 않다면
                      p.setAcceptance((char)48); // 양품 불량품 여부를 false(불량품)으로 설정
                      bad_count++; // 불량품의 개수를 1개 증가
                  }
                  log.info("productList = " + productList);
              }
              /*
                  여기 이후는 for문(생산)이 종료된 이후에 순차적으로 코드 실행
              * */
              lot.setSecond_end(LocalDateTime.now()); // 2공정 종료 시간에 현재 시간을 추가
              try {
                  Thread.sleep(sendMessageDelay);
              } catch (InterruptedException e) {
                  throw new RuntimeException(e);
              }
              stopSend();
              try {
                  processThird();
              } catch (Exception e) {
                  throw new RuntimeException(e);
              }
          };
      }
  
      private Runnable thirdTask(){
          return () -> {
              good_count = 0;
              bad_count = 0;
  
              for (int i = 0; i < productList.size(); i++) {
                  if(productList.get(i).getAcceptance()==48)
                      continue;
                  try {
                      Thread.sleep(productionDelay);
                  } catch (InterruptedException e) {
                      throw new RuntimeException(e);
                  }
                  Random random = new Random();
                  char body = (char)48;
                  int ran = random.nextInt(1, 101);
                  if(ran > 5) { // body가 1일 경우 몸체 조립 완료
                      body = (char)49;
                  }
  
                  // productionList의 i번째 방에 있는 Product를 꺼내어 p에 저장
                  Product p = productList.get(i);
                  // 바디를 저장 ( 0 or 1 )
                  p.setAssembly_body(body);
  
                  if(body == (char)49){ // 만약 assembly_body가 결합이 됐다면
                      good_count++; // 양품의 개수를 1개 증가
                  }
                  else { // 결합이 되지 않았다면
                      p.setAcceptance((char)48); // 양품 불량품 여부를 0(불량품)으로 설정
                      bad_count++; // 불량품의 개수를 1개 증가
                  }
                  log.info("productList = " + productList);
              }
              /*
                  여기 이후는 for문(생산)이 종료된 이후에 순차적으로 코드 실행
              * */
              lot.setThird_end(LocalDateTime.now()); // 3공정 종료 시간에 현재 시간을 추가
              try {
                  Thread.sleep(sendMessageDelay);
              } catch (InterruptedException e) {
                  throw new RuntimeException(e);
              }
              stopSend();
              try {
                  processFourth();
              } catch (Exception e) {
                  throw new RuntimeException(e);
              }
          };
      }
  
      private Runnable fourthTask(){
          return () -> {
              good_count = 0;
              bad_count = 0;
  
              for (int i = 0; i < productList.size(); i++) {
                  if(productList.get(i).getAcceptance()==48)
                      continue;
                  try {
                      Thread.sleep(productionDelay);
                  } catch (InterruptedException e) {
                      throw new RuntimeException(e);
                  }
                  Random random = new Random();
                  // 랜덤의 시작과 끝을 설정할 변수
                  char cap = (char)48;
                  int ran = random.nextInt(1, 101);
                  if(ran > 5) { // cap이 1일 경우 뚜껑 조립 완료
                      cap = (char)49;
                  }
  
                  // productionList의 i번째 방에 있는 Product를 꺼내어 p에 저장
                  Product p = productList.get(i);
                  // 캡을 저장( 0 or 1 )
                  p.setAssembly_cap(cap);
  
                  if(cap == (char)49){ // // 만약 캡이 결합이 됐다면
                      good_count++; // 양품의 개수를 1개 증가
                  }
                  else { // 캡이 결합되지 않았다면
                      p.setAcceptance((char)48); // 양품 불량품 여부를 0(불량품)으로 설정
                      bad_count++; // 불량품의 개수를 1개 증가
                  }
                  log.info("productList = " + productList);
              }
              /*
                  여기 이후는 for문(생산)이 종료된 이후에 순차적으로 코드 실행
              * */
              lot.setFourth_end(LocalDateTime.now()); // 4공정 종료 시간에 현재 시간을 추가
              lot.setEnd_time(LocalDateTime.now()); // 생산 공정 종료 시간에 현재 시간을 추가
              try {
                  Thread.sleep(sendMessageDelay);
              } catch (InterruptedException e) {
                  throw new RuntimeException(e);
              }
              stopSend();
              lot.setS_count(good_count);
              lot.setF_count(lot.getOutput() - lot.getS_count());
              lot.setStatus((char)50);
              try {
                  saveAll();
              } catch (Exception e) {
                  throw new RuntimeException(e);
              }
          };
      }
  }
```

</details>

<br><br><br><br>

<span id="7"></span>
## 🚀7. 트러블 슈팅
<details>
  <summary><b>페이지네이션 대상 지정 문제</b></summary>
  <b>&gt;현상</b><br>
  에러 코드를 가진 제품을 가져오는 기능을 구현하기 위해 JPARepository에서 Page데이터를 추출하는 기능을 사용함. 이때 에러코드를 가지고 있는 제품을 에러 제품이라고 생각해서 그 데이터만 가져오려고 했으나, 페이지네이션 단계에서 전체 데이터를 기준으로 만들어짐<br>
  전체 데이터 기준으로 만들어지다 보니 에러 코드가 있는 제품은 그대로 잘 표시되지만, 에러 코드가 없는 제품은 null값이 반환되어서 리스트의 한 부분을 차지하는 현상이 발생됨.<br>
  또한 한페이지에 10개씩 페이지네이션을 했으나, 어떤 페이지에서는 2개, 어떤 페이지에서는 4개 등 정상적으로 설정된 사이즈만큼 데이터가 출력되지 않음.<br><br>
  
  <b>&gt;원인</b><br>
  페이지네이션 자체가 모든 제품 데이터 대상이다 보니, 페이지 크기와 페이지 넘버가 전체 제품군이 되어버렸음.<br>
  그렇기 때문에 한 페이지마다 에러코드를 가진 제품들의 수가 각기 다른 이유가 일단 전체 제품군이 기준인 페이징이 먼저 되고, 그 다음 에러코드를 가진 것을 필터링 하다보니,<br> 
  한 페이지에 10개씩 제품이 생긴 뒤에 필터링이 되어 갯수가 다 달랐던 것이 었다.
  
  ```java
  @Repository
    public interface ErrorRepository extends JpaRepository<Error, Long> {

    @Query(value = "SELECT * FROM error where error_id = :id", nativeQuery = true)
    Error findByProduct_errorCode(@RequestParam("id") Long id);
  }

  ```

  <b>해결 방법</b>
  &gt; 애초에 대상이 되는 제품군을 선정할 때, 먼저 필터링을 걸어서 에러 코드가 있는 제품만 가져오면 되는 문제였다.

  ```java
   @Query(value = "SELECT * FROM product WHERE error_code != 0", nativeQuery = true)
    Page<Product> findErrorProductAll(Pageable pageable);
  ```
  ```java
  @GetMapping(value = "/products/errors", produces = MediaType.APPLICATION_JSON_VALUE)
    public String showProduct_errors(Model model, @RequestParam(name = "pageNo",defaultValue = "1")int pageNo, @RequestParam(name = "pageSize",defaultValue = "10")int pageSize) {

        int realPage = pageNo - 1;
        Page<Product> page = productService.findAllPageForError(realPage, pageSize);
        List<Product> products = page.getContent();
//        log.info("수정 전 products : " + products);
        
        //제품을 모두 찾는다.
//        List<Product> products = productService.findAll();
//        log.info("수정 후 products : " + products);

        //에러 테이블의 페이지네이션을 위한 페이지 데이터를 가져온다.
//        Page<Error> page_error = errorService.findAllPage(pageNo, pageSize);
        
        //에러 디테일 데이터를 가져오기위한 서비스
        List<Error> errors = errorService.findAllErrors();

        log.info("에러정보 : " + errors);

        model.addAttribute("errors", errors);
        model.addAttribute("products", products);
        model.addAttribute("currentPage", realPage);
        model.addAttribute("totalPages", page.getTotalPages());

        return "products/error_products";
    }
}
  ```


</details>
<details>
  <summary><b>Thyleaf-Bootstrap 모달 기능 사용간 데이터 전송</b></summary>
  <b>&gt;현상</b><br>
  최초 가설을 세울 때에는 '어차피 Thyleaf를 통해서 데이터를 주고받을거니까, 한 html에 있는 form과 modal에서 똑같은 데이터를 쓸 수 있지 않을까?' 싶었음.<br>
  그러나 Controller에서 html로 보낸 제품의 데이터는 List형식의 product'들' 이었고, 모달에서 내가 선택한 특정 product를 가져오기에는 내 가설이 맞지 않았음.
  그래서 modal에서 데이터를 제대로 받아오지 못하는 현상이 있었음<br><br>

  아래 코드에서 '수정'버튼을 누르면 그 제품의 상세정보를 띄울 모달이 나오는데, 그때 모달안에 내가 선택한 제품의 데이터가 들어있어야 하는데, 모달에 데이터를 어떻게 보내야 하는가?
  ```java
    <tbody class="table-group-divider">
        <tr th:each="product : ${products}">
            <td th:text="${product.product_id}"></td>
            <td class="p-md-2 p-1">
                <div class="d-flex align-self-center justify-content-center">
                    <a th:text="${product.lot != null ? product.lot.lot_id : 'N/A'}" th:href="|@{/lots/{id}/detail(id=${product.lot.lot_id})}|" class="fw-bold  link-underline-opacity-0 link-light link-opacity-50-hover"></a>
                </div>
            </td>
            <td th:text="${product.volume + ' ml'}"></td>
            <td th:text= "${product.nib == null} ? '' : ${product.nib + 'mm'}"></td>
            <td th:text="${product.assembly_body}"></td>
            <td th:text="${product.assembly_cap}"></td>
            <td th:if="${product.acceptance == 'P'}" class="text-primary">적합</td>
            <td th:if="${product.acceptance == 'F'}" class="text-danger">부적합</td>
            <td th:text="${product.lot.start_time}"></td>
            <td th:text="${product.lot.end_time}"></td>
            <td>
                <button type="button" class="btn btn-primary"
                        data-bs-toggle="modal" data-bs-target="#qcModal">
                    수정
                </button>
            </td>
        </tr>
        </tbody>
  ```
  <b>&gt;해결 방법</b><br>
  1차 :  
  ```html 
  th:onclick="'openModal(\'' + ${product.product_id} + '\', \'' + ${product.lot.lot_id} + '\')'"> 
  ```
  이렇게 코드를 작성했으나, product 데이터가 안넘어가서 실패<br>

  2차 :
  ```html
  모달로 보내는 버튼에 넣은 코드
  th:attr="data-target=${'#qcModal'+ products}”

  데이터를 받을 모달에 넣은 코드
  th:attr="id='qcModal'+${products}”
  ```
  역시 모달에서 Thyleaf를 사용해서 product를 찾으려 했으나, 인식을 못해서 실패<br>

  3차 :
  ```html
  <td>
	  <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#qcModal" th:attr="onclick='openModal(\'' + ${product.product_id} + '\', \'' + ${product.lot.lot_id} + '\', \'' + ${product.volume} + '\', \'' + ${product.getNib} + '\', \'' +           ${product.assembly_body} + '\', \'' + ${product.assembly_cap} + '\', \'' + ${product.acceptance} + '\', \'' + ${product.lot.getCreatedDate()} + '\', \'' + ${product.lot.getModifiedDate()} + '\')'">
		선택
	  </button>
  </td>
  ```
  데이터를 하나씩 하나씩 보내는 방식으로 모든 데이터를 보냈음. 보낸 데이터는 자바 스크립트를 통해서 다시 모달로 보내주는 방식으로 해결

  ```javascript
    function openModal(productId, lotId, inkCapacity, nibDepth, assemblyBody, assemblyCap, acceptance, createdDate, modifiedDate, comment) {
    // 선택한 제품의 데이터를 모달에 전달
    document.getElementById('productId').innerText = productId;
    document.getElementById('lot_id').innerText = lotId;
    document.getElementById('ink_capacity').innerText = inkCapacity;
    document.getElementById('nib_depth').innerText = nibDepth == "null" ? '미결합' : nibDepth + "mm";
    document.getElementById('assembly_body').innerText = assemblyBody === "Y" ? '결합' : '미결합';
    document.getElementById('assembly_cap').innerText = assemblyCap  === "Y" ? '결합' : '미결합';
    
    if (acceptance === "P") {
    document.getElementById('acceptanceG').checked = true;
    document.getElementById('acceptanceB').checked = false;
    document.getElementById('comment').disabled = true;
    
    } else {
    document.getElementById('acceptanceG').checked = false;
    document.getElementById('acceptanceB').checked = true;
    document.getElementById('comment').disabled = false;
    }
    document.getElementById('start_date').innerText = createdDate;
    document.getElementById('end_date').innerText = modifiedDate;
    
    document.getElementById('comment').innerText = comment;
    if (comment === "null") {
        document.getElementById('comment').innerText ="";
    }
    $('#qcModal').modal('show');
    // productId를 hidden 필드에 설정
        document.getElementById('product_id').value = productId;
    }
  ```

  ```html
	<div class="modal fade" id="qcModal" tabindex="-1" aria-labelledby="qcLabel" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered">
            <div class="modal-content">
                <div class="modal-header bg-secondary-subtle">
                    <h1 class="modal-title fs-2 fw-bold" id="qclLabel">품질관리 데이터 등록</h1>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body px-5" style="background-color: rgba(41,17,8,0.22);">
                    <form class="row g-3" method="post" th:action="@{/products/commentSave}">
                        <div class="col-6">
                            <h5>제품 번호: <span id="productId" class="fw-bold"></span></h5>
                        </div>
                        <div class="col-md-6">
                            <h5>Lot 번호: <span id="lot_id" class="fw-bold"></span></h5>
                        </div>
                        <hr>
                        <div class="col-md-6">
                            <h5>잉크 용량: <span id="ink_capacity" class="fw-bold"></span> ml</h5>
                        </div>
                        <div class="col-md-6">
                            <h5>닙 깊이: <span id="nib_depth" class="fw-bold"></span></h5>
                        </div>
                        <hr>
                        <div class="col-md-6">
                            <h5 class="fs-6">바디 결합 여부: <span id="assembly_body" class="fw-bold fs-6"></span></h5>
                        </div>
                        <div class="col-md-6">
                            <h5 class="fs-6">뚜껑 결합 여부: <span id="assembly_cap" class="fw-bold fs-6"></span></h5>
                        </div>
                        <hr>
                        <div class="col-md-12">
                            <h5 class="mb-3">적합/부적합 여부: </h5>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" name="acceptance" id="acceptanceG" value="P">
                                <label class="form-check-label fw-bold" for="acceptanceG">
                                    적합
                                </label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" name="acceptance" id="acceptanceB" value="F">
                                <label class="form-check-label fw-bold" for="acceptanceB">
                                    부적합
                                </label>
                            </div>
                        </div>
                        <hr>
                        <div class="col-md-12">
                            <h5>생산 시작: <span id="start_date" class="fw-bold"></span></h5>
                        </div>
                        <div class="col-md-12">
                            <h5>생산 종료: <span id="end_date" class="fw-bold"></span></h5>
                        </div>
                        <hr>
                        <!--                        comment에 들어갈 내용 적는 부분 -->
                        <div class="input-group col-md-12 input-group-lg">
                            <span class="input-group-text fw-bold">세부 부적합 <br>사유 </span>
                            <textarea id="comment" name="comment" class="form-control" rows="8" aria-label="세부 부적합 사유">

                            </textarea>
                        </div>
                        <!--                        내가 선택한 제품의 comment를 바꿔야하니까 그 제품을 특정할 수 있는 아이디를 form에 부여-->
                        <input type="hidden" id="product_id" name="product_id">
                    </form>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-danger" data-bs-dismiss="modal">닫기</button>
                        <!--                        onclick시 Conroller에 데이터를 보내는 자바 스크립트 실행-->
                        <button type="submit" class="btn btn-primary" onclick="saveComment()">수정</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
  ```
</details>
<br><br><br><br>

<span id="8"></span>
## 💥8. 리팩토링 필요
- **예외 처리**
  - Controller에 맵핑되지 않은 주소 요청이 올 경우 **Whitelabel Error Page가 아닌 만들어둔 400번, 500번 에러 페이지로 이동**할 수 있도록 설정 필요
- **생산 지시의 규격 추가**
  - 현재 기능에서는 1개의 규격으로만 생산을 하게 되어있지만 **규격이 추가가 될 경우 여러 개의 규격 중 선택**하여 생산을 할 수 있도록 로직 변경 필요
- **생산 중단 기능 확장**
  - 여러 개의 생산 지시를 내린 후 생산 중단 기능을 누를 경우 생산 지시가 모두 삭제 되어 **생산 중단 버튼 클릭 시 N개의 생산 지시 중 1개만 선택하여 해당 지시를 취소**할 수 있도록 로직 변경 필요
  - **N번 공정에서 생산 도중 생산 중단 버튼 클릭 시 모두 삭제,** 실제 업무로 보면 3공정에서 중단 시 1~3공정까지 만들어진 모든 제품을 모두 버리고 1공정부터 새로 만들게 되는 식의 로직이기 때문에 반드시 리팩토링 필요
- **모니터링 리팩토링**
  - 생산 지시 후 생산이 되고 있는 중에 다른 사용자가 모니터링 페이지에 접속하면 데이터를 정상적으로 수신할 수 있지만, 생산 중에만 데이터를 보내는 것이기 때문에 **생산 공정이 돌아가지 않을 때 모니터링 페이지 접속할 경우 가장 마지막의 데이터를 클라이언트에게 데이터를 전송**하는 로직이 필요
<br><br><br><br>

<span id="9"></span>
## ⭕9. 리팩토링 완료
- **페이지 필터**
  - **로그인이 되지 않은 상태(세션에 로그인 정보가 없는 상태)에서 로그인 이외의 페이지를 요청을 할 경우 접근이 불가능**하고 로그인을 유도하기 위해 로그인 페이지로 이동
<br><br><br><br>

<span id="10"></span>
## 🙆‍♂️10. 느낀 점 및 아쉬운 점
부족한 지식이지만 열심히 프로젝트에 임했습니다. 결과가 마음에 100% 차는건 아니지만, 제가 무언가를 끝마침했다는 것에 뿌듯함을 느낄 수 있었습니다. <br>
이번 프로젝트를 통해서 스프링을 활용한 프로젝트 구현에 많은 경험을 할 수 있었습니다. 백엔드 개발에 있어서 내가 부족한 부분은 무었이었는지, 앞으로 더 채워나갈 지식은 무었이 있을지 고민도 할 수 있는 귀중한 경험이었다고 생각합니다. <br>
이후에는 백엔드 개발에 있어서 제가 무엇을 공부해야 할지 고민하고 부족한 부분을 채워나가는 성장하는 사람이 되도록 노력할 예정입니다. <br>
