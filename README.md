# test4

<!-- [JavaScript] 실시간 글자 수 / 단어 수 카운터 -->
<!DOCTYPE html>
<html>
<head>
  <style>
    /* 입력창 및 레이아웃 기본 스타일 지정 */
    body { font-family: sans-serif; padding: 20px; max-width: 500px; margin: 0 auto; }
    textarea { width: 100%; height: 120px; font-size: 1rem; padding: 8px; box-sizing: border-box; }
    .result { margin-top: 10px; font-weight: bold; color: #333; }
  </style>
</head>
<body>
  <h2>글자 수 카운터</h2>
  <!-- 사용자 글자 입력 영역 -->
  <textarea id="textInput" placeholder="여기에 텍스트를 입력하세요..." oninput="countText()"></textarea>
  
  <!-- 결과를 출력할 태그 -->
  <div class="result" id="resultDisplay">글자 수: 0자 (공백 제외: 0자) | 단어 수: 0개</div>

  <script>
    // 입력창에 글자가 들어올 때마다 호출되는 함수
    function countText() {
      const text = document.getElementById('textInput').value; // 입력된 전체 문자열 가져오기
      
      const totalChar = text.length; // 공백 포함 전체 글자 수
      const noSpaceChar = text.replace(/\s+/g, '').length; // 공백을 제거한 글자 수
      
      // 공백으로 단어를 분리한 뒤 빈 문자열 항목 제거 후 단어 수 계산
      const wordCount = text.trim() === '' ? 0 : text.trim().split(/\s+/).length;

      // 계산 결과를 화면에 적용
      document.getElementById('resultDisplay').innerText = 
        `글자 수: ${totalChar}자 (공백 제외: ${noSpaceChar}자) | 단어 수: ${wordCount}개`;
    }
  </script>
</body>
</html>
