# Technical Service Case Study Detail Page Generator

## Purpose
This agent instruction generates detailed case study pages for the Office 365 Agile implementation guide. Each case study follows the same structure as `week5.html` - `week10.html`, providing step-by-step practical guidance for Technical Service teams.

---

## How to Use

When the user requests a detailed case study page, follow these steps:

### Step 1: Identify the Case
Ask which case number (1-20) from `cases.html` should be expanded. Reference the case summary:

| Case | Category | Title |
|------|----------|-------|
| 01 | Inventory | MRO 부품 과잉재고 해소 |
| 02 | Inventory | 긴급 부품 품절 제로화 |
| 03 | R&M Cost | 예방정비 스케줄 최적화 |
| 04 | R&M Cost | 외주 정비 비용 투명화 |
| 05 | OT | 설비 이력 관리 디지털화 |
| 06 | OT | 작업 지시서 전자화 |
| 07 | Safety | 아차사고 신속 보고 체계 |
| 08 | Safety | 안전 교육 이수 관리 |
| 09 | Energy | 압축공기 누설 관리 |
| 10 | Energy | 조명 에너지 절감 |
| 11 | Inventory | 부품 바코드 시스템 도입 |
| 12 | R&M Cost | 설비 고장 패턴 분석 |
| 13 | OT | 전력 모니터링 대시보드 |
| 14 | Safety | LOTO 관리 디지털화 |
| 15 | Inventory | 공용 공구 관리 시스템 |
| 16 | R&M Cost | 정비 작업 표준화 |
| 17 | OT | 센서 이상 자동 알림 |
| 18 | Energy | 스팀 트랩 점검 관리 |
| 19 | Safety | 위험성 평가 디지털화 |
| 20 | R&M Cost | 정비 KPI 대시보드 |

### Step 2: Generate the Detail Page

Create file: `case{XX}.html` (e.g., `case01.html`)

---

## Required Page Structure

### 1. HTML Head
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Case {XX}: {Title} | Technical Service Team</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700;900&family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <link rel="stylesheet" href="styles.css">
    <link rel="stylesheet" href="week-detail.css">
    <link rel="stylesheet" href="case-study.css">
</head>
```

### 2. Navigation
```html
<nav class="week-nav">
    <a href="cases.html" class="nav-back"><i class="fas fa-arrow-left"></i> 사례 목록</a>
    <div class="week-indicator">
        <a href="case{XX-1}.html" class="prev"><i class="fas fa-arrow-left"></i> Case {XX-1}</a>
        <span class="current case">Case {XX}</span>
        <a href="case{XX+1}.html" class="next">Case {XX+1} <i class="fas fa-arrow-right"></i></a>
    </div>
</nav>
```

### 3. Case Study Banner
Use appropriate theme based on category:
- Inventory: `inventory` theme (purple gradient)
- R&M Cost: `rm` theme (orange gradient)  
- OT: `ot` theme (green gradient)
- Safety: `safety` theme (red gradient)
- Energy: `energy` theme (cyan gradient)

```html
<div class="case-study-banner {category}-theme">
    <div class="container">
        <span class="case-badge"><i class="fas fa-industry"></i> Technical Service Team 실전 사례</span>
        <h2>Case {XX}: {Title}</h2>
        <p>{One-line description}</p>
    </div>
</div>
```

### 4. Hero Section
```html
<section class="week-hero case{XX}-theme">
    <div class="hero-content">
        <span class="week-badge">Case {XX} | {Category}</span>
        <h1>{Emoji} {Title}</h1>
        <p>{Detailed description of the improvement}</p>
        <div class="kpi-focus">
            <!-- 3 KPI items relevant to this case -->
        </div>
    </div>
</section>
```

### 5. Problem Definition Section
```html
<section class="sprint-goal">
    <div class="container">
        <div class="goal-card {category}">
            <h2><i class="fas fa-exclamation-circle"></i> 문제 상황</h2>
            <div class="scenario-box">
                <h4><i class="fas fa-users"></i> 현장의 목소리</h4>
                <p>
                    {Detailed problem description}<br>
                    <em>"{Actual quote from team member describing the pain point}"</em>
                </p>
            </div>
            <div class="goal-metrics">
                <div class="metric">
                    <span class="metric-label">Before 상태</span>
                    <span class="metric-value">{Before metric}</span>
                </div>
                <div class="metric">
                    <span class="metric-label">목표</span>
                    <span class="metric-value">{Target metric}</span>
                </div>
                <div class="metric">
                    <span class="metric-label">개선 기간</span>
                    <span class="metric-value">{Duration}</span>
                </div>
            </div>
        </div>
    </div>
</section>
```

### 6. Step-by-Step Guide (MOST IMPORTANT)
Create 4-6 detailed steps, each with:
- Step number and tool icon
- Timing (day/time)
- Detailed instructions with sub-steps
- Example data, templates, or screenshots descriptions
- Tips and best practices

```html
<section class="step-guide">
    <div class="container">
        <h2 class="section-title">📋 실행 가이드</h2>

        <div class="step-card" id="step1">
            <div class="step-header">
                <div class="step-number">1</div>
                <div class="step-tool {tool-class}"><i class="{tool-icon}"></i><span>{Tool Name}</span></div>
                <span class="step-time"><i class="fas fa-clock"></i> {Timing}</span>
            </div>
            <h3>{Step Title}</h3>
            <div class="step-content">
                <div class="instructions">
                    <h4><i class="fas fa-list-ol"></i> 실행 순서</h4>
                    
                    <div class="instruction-step">
                        <span class="instruction-num">1-1</span>
                        <div class="instruction-content">
                            <h5>{Sub-step title}</h5>
                            <p>{Detailed instruction}</p>
                            <!-- Include relevant examples: tables, code, templates -->
                        </div>
                    </div>
                    
                    <!-- More instruction-steps... -->
                </div>
                
                <div class="tip-box">
                    💡 <strong>Tip:</strong> {Practical advice}
                </div>
            </div>
        </div>

        <!-- Repeat for steps 2-6 -->
    </div>
</section>
```

### 7. Tool-Specific Content Examples

#### For Excel steps:
```html
<div class="excel-template">
    <h5>{Template Name}.xlsx 구조:</h5>
    <table class="excel-table">
        <thead>
            <tr>
                <th>Column 1</th>
                <th>Column 2</th>
                <!-- More columns -->
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Sample data</td>
                <td>=FORMULA</td>
            </tr>
        </tbody>
    </table>
</div>
```

#### For Planner steps:
```html
<div class="backlog-example">
    <table>
        <thead>
            <tr>
                <th>태스크</th>
                <th>담당자</th>
                <th>SP</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Task description</td>
                <td>김OO</td>
                <td>3</td>
            </tr>
        </tbody>
    </table>
    <p class="total-sp">총 스토리 포인트: <strong>XX</strong></p>
</div>
```

#### For Teams/Daily Standup:
```html
<div class="standup-example">
    <h4><i class="fas fa-comments"></i> 스탠드업 예시</h4>
    <div class="standup-person">
        <strong>담당자명 (역할)</strong>
        <ul>
            <li>🟢 어제: {What was done}</li>
            <li>🔵 오늘: {What will be done}</li>
            <li>🔴 블로커: {Any blockers}</li>
        </ul>
    </div>
</div>
```

#### For Power Automate:
```html
<div class="automation-flow">
    <h5>자동화 흐름:</h5>
    <div class="flow-steps">
        <div class="flow-step">트리거: {Trigger event}</div>
        <div class="flow-arrow">↓</div>
        <div class="flow-step">조건: {Condition}</div>
        <div class="flow-arrow">↓</div>
        <div class="flow-step">액션: {Action}</div>
    </div>
</div>
```

### 8. Results Section
```html
<section class="week-summary">
    <div class="container">
        <div class="summary-card value-card">
            <h2><i class="fas fa-chart-line"></i> 개선 결과</h2>
            <div class="result-grid">
                <div class="result-item">
                    <i class="fas fa-{icon}"></i>
                    <h4>{Result metric}</h4>
                    <p>{Description}</p>
                </div>
                <!-- 4 result items -->
            </div>
            
            <div class="value-metrics">
                <div class="value-item">
                    <div class="value-icon"><i class="fas fa-{icon}"></i></div>
                    <div class="value-info">
                        <h4>{Benefit title}</h4>
                        <p>{Benefit description}</p>
                        <span class="value-tag">{Quantified value}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>
```

### 9. Lessons Learned / Retrospective
```html
<section class="step-guide">
    <div class="container">
        <div class="step-card">
            <h3><i class="fas fa-lightbulb"></i> 핵심 교훈</h3>
            <div class="retro-board">
                <div class="retro-column start">
                    <h4>✅ 시작할 것 (Start)</h4>
                    <ul>
                        <li>{New practice to adopt}</li>
                    </ul>
                </div>
                <div class="retro-column stop">
                    <h4>🛑 멈출 것 (Stop)</h4>
                    <ul>
                        <li>{Practice to stop}</li>
                    </ul>
                </div>
                <div class="retro-column continue">
                    <h4>🔄 계속할 것 (Continue)</h4>
                    <ul>
                        <li>{Practice to continue}</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</section>
```

### 10. Navigation to Next Case
```html
<section class="next-week-preview">
    <div class="container">
        <div class="preview-card case-preview {category}">
            <span class="preview-label">다음 사례</span>
            <h2>Case {XX+1}: {Next case title}</h2>
            <p>{Next case description}</p>
            <a href="case{XX+1}.html" class="btn btn-primary">다음 사례 보기 <i class="fas fa-arrow-right"></i></a>
        </div>
    </div>
</section>
```

### 11. Footer
```html
<footer class="footer">
    <p>© 2025 Office 365 Agile Action Plan | <a href="cases.html">사례 목록</a> | <a href="index.html">전체 로드맵</a></p>
</footer>
<script src="script.js"></script>
</body>
</html>
```

---

## Content Guidelines

### Tone & Style
- Write in Korean for all user-facing content
- Use practical, actionable language
- Include specific examples with realistic data
- Reference actual Office 365 features and menus

### Technical Accuracy
- Excel formulas must be syntactically correct
- Power Automate flows should reflect actual connector capabilities
- Planner board structures should match real Microsoft Planner

### Realism
- Use believable Korean names (김OO, 이OO, 박OO)
- Include realistic metrics for manufacturing environments
- Reference common MRO parts, equipment types, safety standards

### Length
- Each step-card should have 2-4 instruction-steps
- Total page should be 300-500 lines of HTML
- Include at least one template/example per step

---

## Tool Icon Reference

| Tool | Class | Icon |
|------|-------|------|
| Teams | `teams` | `fab fa-microsoft` |
| Planner | `planner` | `fas fa-tasks` |
| Excel | `excel` | `fas fa-table` |
| SharePoint | `sharepoint` | `fas fa-share-alt` |
| OneNote | `onenote` | `fas fa-book` |
| Power Automate | `powerautomate` | `fas fa-cog` |
| Forms | `forms` | `fas fa-clipboard-list` |
| Power BI | `powerbi` | `fas fa-chart-bar` |

---

## Category Theme Colors

| Category | Banner Class | Hero Theme |
|----------|--------------|------------|
| Inventory | `case-study-banner` | `linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%)` |
| R&M Cost | `case-study-banner rm-theme` | `linear-gradient(135deg, #f59e0b 0%, #d97706 100%)` |
| OT | `case-study-banner ot-theme` | `linear-gradient(135deg, #10b981 0%, #059669 100%)` |
| Safety | `case-study-banner safety-theme` | `linear-gradient(135deg, #ef4444 0%, #dc2626 100%)` |
| Energy | `case-study-banner energy-theme` | `linear-gradient(135deg, #06b6d4 0%, #0891b2 100%)` |

---

## Example Prompt for Generating a Case

When user says: "Case 07 상세 페이지 만들어줘"

1. Read this instruction file
2. Reference `cases.html` for Case 07 summary
3. Generate `case07.html` following the structure above
4. Include 5 detailed steps specific to 아차사고 신속 보고 체계:
   - Step 1: Forms로 신고 양식 설계
   - Step 2: Power Automate로 알림 흐름 구성
   - Step 3: Planner에 후속조치 태스크 자동생성
   - Step 4: Teams 채널에서 진행상황 모니터링
   - Step 5: Excel/Power BI로 통계 대시보드 구축
5. Commit the file after creation

---

## File Naming Convention

- Detail pages: `case01.html`, `case02.html`, ... `case20.html`
- All files go in: `/Users/proxsolver/2026/1pager/o365/`

---

## After Generation Checklist

- [ ] File created with correct name
- [ ] All CSS files linked correctly
- [ ] Navigation links work (prev/next)
- [ ] At least 4 step-cards included
- [ ] Realistic examples and templates
- [ ] Proper Korean content
- [ ] Footer with navigation links
- [ ] Git commit with descriptive message
