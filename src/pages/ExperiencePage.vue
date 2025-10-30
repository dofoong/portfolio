<template>
  <div class="q-ma-md">
    <TargetHeader header="Experience" />
    <div class="column q-my-md">
      <div class="row full-width">
        <div style="width: 200px; font-size: 1.4rem; font-weight: 500">Frontend</div>
        <div class="col">
          <!-- fe case 1 -->
          <q-expansion-item
            expand-separator
            label="Case 1. 고객사 맞춤 Tabulator 기반 엑셀형 데이터 편집 기능 구현"
            header-class="case-header"
            class="q-mb-sm"
          >
            <div class="q-pb-sm">
              <div class="case-header q-my-sm">문제 상황</div>
              <p>
                고객사의 기존 MES 시스템은 노후화된 <strong>Delphi 기반</strong>으로, 웹 전환
                과정에서 <strong>엑셀 형태의 입력 방식이 사라질 것에 대한 사용자 반발</strong>이
                있었습니다.<br />
                운영 담당자들이 다년간 익숙해진 엑셀 스타일의 입력 흐름을 유지하지 않으면 작업
                효율이 오히려 떨어질 우려가 있었습니다.
              </p>

              <div class="case-header">접근 방식</div>
              <ul>
                <li>
                  기존 엑셀 입력 패턴을 분석하여,
                  <strong>셀 단위 편집·정렬·복사/붙여넣기 등 사용자 습관을 그대로 반영</strong
                  >했습니다.
                </li>
                <li>
                  Vue.js(Quasar) 기반 프론트엔드에 <strong>Tabulator 라이브러리</strong>를 도입하고,
                  기본 기능을 커스터마이징하여 엑셀과 거의 동일한 입력 인터랙션을 제공했습니다.
                </li>
                <li>
                  백엔드 API와의 실시간 연동 구조를 설계하여, 셀 수정 시 DB에 즉시 반영되도록
                  구현했습니다.
                </li>
                <li>
                  사용자별 권한 및 데이터 검증 로직을 추가하여 <strong>데이터 무결성</strong>과
                  <strong>사용자 안정성</strong>을 동시에 확보했습니다.
                </li>
              </ul>

              <div class="case-header">해결 결과</div>
              <ul>
                <li>
                  <strong>엑셀과 유사한 입력 경험을 유지한 채 웹 환경으로 성공적 전환.</strong>
                </li>
                <li>
                  사용자 교육 없이 기존 업무 흐름을 그대로 유지할 수 있었고, 시스템 이관 후에도
                  <strong>입력 효율 및 데이터 관리 정확도 개선.</strong>
                </li>
                <li>
                  고객사로부터 “기존 환경보다 편리하다”는 피드백을 받으며, 이후 다른 고객사 웹 전환
                  프로젝트에도 동일 구조가 재사용되었습니다.
                </li>
              </ul>
            </div>
          </q-expansion-item>
          <!-- fe case 2 -->
          <q-expansion-item
            expand-separator
            label="Case 2. Chart.js 기반 KPI 대시보드 구축"
            header-class="case-header"
            class="q-mb-sm"
          >
            <div class="q-pb-sm">
              <div class="case-header q-my-sm">문제 상황</div>
              <p>
                고객사의 기존 KPI 관리 방식은 <strong>엑셀 기반 수기 보고</strong>로 진행되어 실시간
                데이터 확인이 불가능하고, 관리자의 보고 과정이 복잡했습니다.<br />
                주요 지표(생산량, 불량률, 가동률 등)가 여러 데이터 소스에 분산되어 있어 한눈에
                파악하기 어려운 문제가 있었습니다.
              </p>

              <div class="case-header">접근 방식</div>
              <ul>
                <li>
                  설비 및 사용자 입력 데이터를 서버에서 실시간으로 산출할 수 있도록
                  <strong>Kotlin + REST API</strong> 기반의 데이터 수집 구조를 설계했습니다.
                </li>
                <li>
                  <strong>Chart.js</strong>를 활용해 KPI 데이터를 시각화하고, 필터별 조회 및 실시간
                  갱신 기능을 제공했습니다.
                </li>
                <li>
                  Vue.js(Quasar) 컴포넌트 내부에 <strong>데이터 캐싱 로직</strong>을 추가하여
                  대시보드의 응답 속도를 개선하고 네트워크 부하를 줄였습니다.
                </li>
                <li>
                  관리자와 현장 담당자 모두 직관적으로 지표를 이해할 수 있도록
                  <strong>차트 타입(막대, 선, 도넛 등)</strong>을 KPI 특성에 맞게 구성했습니다.
                </li>
              </ul>

              <div class="case-header">해결 결과</div>
              <ul>
                <li>
                  주요 KPI를 실시간으로 조회할 수 있는 <strong>웹 대시보드 화면</strong>을
                  구현했습니다.
                </li>
                <li>
                  기존 엑셀 기반 보고 과정을 자동화하여 관리자의 보고 시간 단축 및 데이터 신뢰성을
                  향상시켰습니다.
                </li>
                <li>
                  KPI 데이터 활용도가 높아져, <strong>운영 효율성과 의사결정 속도</strong>가
                  개선되었습니다.
                </li>
              </ul>
            </div>
          </q-expansion-item>
          <!-- fe case 3 -->
          <q-expansion-item
            expand-separator
            label="Case 3. Tabulator 내 CJK 입력 처리 이슈 해결"
            header-class="case-header"
            class="q-mb-sm"
          >
            <div class="q-pb-sm">
              <div class="case-header q-my-sm">문제 상황</div>
              <p>
                Tabulator 기본 입력 폼에서 <strong>한중일(CJK)</strong> 문자 입력 시
                <strong>글자 깨짐·중복 입력·포커스 손실</strong> 문제가 발생했습니다.<br />
                이는 IME(입력기) 조합 중 keydown 이벤트가 조기에 처리되어 Vue.js(Quasar) 환경에서
                조합 중간 입력이 반영되는 현상 때문이었습니다.<br />
                특히 한글 입력 빈도가 높은 키오스크 환경에서는 입력 오류로 인해 데이터 신뢰도와
                사용자 경험이 저하되는 문제가 있었습니다.
              </p>

              <div class="case-header">접근 방식</div>
              <ul>
                <li>
                  Tabulator의 기본 <strong>Editor 구조</strong>를 분석한 뒤, 내부 input 엘리먼트를
                  대체하는 <strong>커스텀 인풋 컴포넌트</strong>를 직접 구현했습니다.
                </li>
                <li>
                  compositionstart, compositionupdate, compositionend 이벤트를 직접 제어하여 IME
                  조합 중에는 입력값이 반영되지 않도록 처리했습니다.
                </li>
                <li>
                  조합 완료(compositionend) 시점에만 값이 DB로 전달되도록 수정하여 중복 입력 및
                  포커스 손실 문제를 방지했습니다.
                </li>
                <li>
                  Chrome, Edge 등 주요 브라우저 환경에서 테스트를 수행하고, Quasar 기반
                  키오스크에서도 동일하게 동작하도록 최적화했습니다.
                </li>
              </ul>

              <div class="case-header">해결 결과</div>
              <ul>
                <li>
                  CJK 문자 입력 시 발생하던
                  <strong>깨짐·중복 입력·포커스 초기화 문제 완전 해결.</strong>
                </li>
                <li>
                  한글 입력이 많은 현장 키오스크 환경에서도 안정적인 입력 경험을 제공했습니다.
                </li>
                <li>
                  Tabulator의 구조적 한계를 분석하고 Vue.js 환경에 맞게 커스터마이징한
                  <strong>입력 처리 로직을 사내 표준으로 정립</strong>하여 이후 프로젝트에
                  재사용했습니다.
                </li>
              </ul>
            </div>
          </q-expansion-item>
        </div>
      </div>
      <div class="row">
        <div style="width: 200px; font-size: 1.4rem; font-weight: 500">Backend</div>
        <div class="col">
          <!-- be case 1 -->
          <q-expansion-item
            expand-separator
            label="Case 1. 대용량 Stored Procedure 성능 최적화 (10분 → 2초)"
            header-class="case-header"
            class="q-mb-sm"
          >
            <div class="q-pb-sm">
              <div class="case-header q-my-sm">문제 상황</div>
              <p>
                기존 Delphi 기반 솔루션에서 사용되던 <strong>Stored Procedure</strong>는 복잡한 다중
                JOIN과 불필요한 서브쿼리로 인해 <strong>10분 이상</strong> 소요되었습니다.<br />
                이는 주요 생산 현황 데이터를 실시간으로 확인하지 못하게 만들어 관리자 보고 및
                의사결정에 큰 병목으로 작용했습니다.
              </p>

              <div class="case-header">접근 방식</div>
              <ul>
                <li>
                  기존 SP를 분석하여 <strong>불필요한 중첩 쿼리</strong>와
                  <strong>비효율적 인덱스</strong>를 제거했습니다.
                </li>
                <li>
                  복잡한 데이터 집계를 <strong>임시 테이블</strong> 기반으로 분리하여 단계별 연산을
                  수행하도록 구조화했습니다.
                </li>
                <li>
                  핵심 조회 구간에 <strong>Clustered Index / Covering Index</strong>를 추가하여
                  I/O를 최소화했습니다.
                </li>
                <li>
                  Kotlin(Spring Boot) 기반으로 <strong>비동기 처리 로직</strong>을 구성해 결과를
                  캐싱 후 Chart.js 대시보드에 제공했습니다.
                </li>
              </ul>

              <div class="case-header">해결 결과</div>
              <ul>
                <li>
                  프로시저 실행 속도를 <strong>10분 이상 → 2초 이내</strong>로 단축시켰습니다.
                </li>
                <li>서버 부하가 감소하고, KPI 대시보드의 실시간 갱신이 가능해졌습니다.</li>
                <li>
                  해당 구조는 이후 다른 고객사 프로젝트에서도 재사용되어
                  <strong>표준화된 성능 개선 템플릿</strong>으로 자리잡았습니다.
                </li>
              </ul>
            </div>
          </q-expansion-item>
          <!-- be case 2 -->
          <q-expansion-item
            expand-separator
            label="Case 2. Delphi 기반 시스템의 Spring Boot 리팩토링"
            header-class="case-header"
            class="q-mb-sm"
          >
            <div class="q-pb-sm">
              <div class="case-header q-my-sm">문제 상황</div>
              <p>
                고객사의 기존 <strong>Delphi 기반 근태관리 시스템</strong>은 유지보수 인력 부족과
                기술적 한계로 인해 버그가 빈번했고, 데이터 접근 속도도 느렸습니다.<br />
                시스템 노후화로 인해 웹 전환이 필수적이었으며, 기존 DB 구조를 그대로 활용해야 하는
                제약이 있었습니다.
              </p>

              <div class="case-header">접근 방식</div>
              <ul>
                <li>
                  기존 DB 스키마를 분석하여 <strong>JPA Entity</strong>로 재구성하고, 데이터 접근
                  계층을 <strong>Spring Data JPA + QueryDSL</strong> 기반으로 리팩토링했습니다.
                </li>
                <li>
                  데이터 변경이 빈번한 구간은 <strong>MyBatis</strong>로 분리하여 관리하며 성능과
                  유지보수성을 모두 확보했습니다.
                </li>
                <li>
                  기존 Delphi 로직의 흐름을 Kotlin으로 재작성하면서
                  <strong>Null 안정성과 예외 처리</strong>를 강화했습니다.
                </li>
                <li>
                  폐쇄망 환경 배포를 위해 <strong>NGINX + Spring Boot 내장 Tomcat</strong>을 조합해
                  독립 실행 구조를 설계했습니다.
                </li>
              </ul>

              <div class="case-header">해결 결과</div>
              <ul>
                <li>
                  기존 Delphi 시스템을 완전한 <strong>웹 환경으로 성공적으로 이관</strong>했습니다.
                </li>
                <li>
                  유지보수성과 확장성이 개선되어, 신규 기능 추가 시 개발 속도가 약
                  <strong>30% 향상</strong>되었습니다.
                </li>
                <li>폐쇄망 환경에서도 안정적인 서비스 운영이 가능해졌습니다.</li>
              </ul>
            </div>
          </q-expansion-item>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
import TargetHeader from 'src/components/TargetHeader.vue';
</script>
