# RC_2nd_Challenge
(주) 소프트스퀘어드 의 부트캠프인 '라이징캠프' 2주차 도전미션 과제입니다.

카카오뱅크 클론입니다.

## 핵심개념

📕 Material Design을 잘 활용하자.

📕 생동감 있는 앱을 위해 Awesome UI도 활용해보자

## 에러사항

💢 SearchView 를 사용해 검색화면을 구성할 시, 돋보기 이모티콘이 원본에 비해 과도하게 우측으로 치우치는 이슈가 있었다.

💢 CardView 사용시 은은한 그림자를 원했으나, 테두리처럼 생긴 그림자로 나오는 이슈가 있었다.

💢 Netflix 화면을 구성하고자 했을 당시, 화면 스크롤에 따라 상단바가 특정 위치까지 올라가고 색상이 변해야 한다. 색상변환은 Scroll Event 를 사용하려 했으나, 스크롤 속도에 따른 이슈가 있었고, 화면 스크롤에 따라 상단바 스크롤 이슈 또한 있었다.

💢 카카오페이 중단 ViewPager2 화면 구성에서, 3*3 격자무늬를 동적으로 합병해줘야 했었다.

## 피드백

🤦🏻 원본 앱에서도 검색창 클릭시 별개의 Dialog / Layout 으로 넘어가는 구성으로 보아, 굳이 SearchView 를 사용 할 필요가 없다고 판단, LinearLayout 으로 구성했다.

🤦🏻 해당 CardView를 둘러싸는 Layout 하나를 더 생성한 후, 색상에 약간의 차이를 주는 방식으로 구현했다.

🤦🏻 아무리 찾아보고 이것저것 건드려봐도 도저히 방법이 떠오르지 않았다..

→ 상단바 색상이 투명 → 반투명한 검은색으로 스크롤에 따라 변경되고, 상단바에 앱 화면이 비쳐보이는 것으로 보아 FrameLayout과 Coordinator Layout, Collapsing Toolbar Layout 을 사용한 것으로 추측되지만,      FrameLayout 스크롤 시 Collapsing Toolbar 또한 스크롤 동작을 동일하게 하는 방법을 찾을 수 없었다.

🤦🏻 결국 Fragment를 구성하는 XML파일은 하나로 두고, FrameLayout을 사용하여 ViewPager의 Position에 따라서 Visibility를 변경하는 방식으로 구현했다. 질문방에서 답변해주신 사항을 검색해본 결과, 하나하나의 셀에 지정을 해줘야 하는 것으로 보인다. 그러한 방법보다는 XML에서 구성 후 Visibility를 Visible ↔ Gone 으로 사용하는 방식이 조금 더 효율적일것 같다고 생각했다.
