# Static Promo Web Template

정적 프로모션 웹사이트를 위한 템플릿 저장소입니다.  
GitHub Actions를 통해 S3 + CloudFront로 자동 배포됩니다.

## 사용 방법

### 1. 이 템플릿으로 새 저장소 생성

GitHub에서 "Use this template" 버튼을 클릭하거나:

```bash
gh repo create [저장소명] --template ridi-ax/static-promo-template
```

### 2. GitHub Secrets 설정

저장소 Settings > Secrets and variables > Actions에서 다음 시크릿을 설정하세요:

| Secret 이름 | 설명 |
|------------|------|
| `AWS_IAM_ROLE_ARN` | AWS IAM Role ARN (인프라팀에서 제공) |
| `S3_BUCKET_NAME` | S3 버킷 이름 |
| `CLOUDFRONT_DIST_ID` | CloudFront Distribution ID |

### 3. 프로젝트 구조

```
your-project/
├── .github/
│   └── workflows/
│       └── deploy.yml      # 배포 워크플로우
├── project-name/           # 프로젝트별 폴더
│   ├── index.html
│   ├── styles.css
│   └── script.js
├── another-project/        # 여러 프로젝트 가능
│   └── index.html
└── README.md
```

### 4. 배포

`main` 브랜치에 푸시하면 자동으로 배포됩니다.

```bash
git add .
git commit -m "Add new promo page"
git push origin main
```

## 배포 제외 항목

다음 파일/폴더는 S3에 업로드되지 않습니다:
- `.git/`
- `.github/`
- `README.md`
- `*.md` (모든 마크다운 파일)

## 예시 프로젝트

`example/` 폴더에 기본 예시가 포함되어 있습니다.

## 문의

인프라 관련 문의: 인프라팀
