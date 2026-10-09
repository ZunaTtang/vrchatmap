# vrchatmap — 스튜디오 벽면 이미지

VRChat 버튜버 방송 스튜디오 월드("스트리트 도그하우스 로프트")의 **벽면 포스터 이미지**를 올려두는 저장소입니다.
월드는 입장할 때 이 저장소의 GitHub Pages 주소에서 이미지를 불러오므로,
**여기서 파일만 바꾸면 월드를 다시 업로드하지 않아도 벽 그림이 바뀝니다.**

```
https://zunattang.github.io/vrchatmap/wall/wall_<슬롯>.png
```

## 이미지 바꾸는 방법 (웹에서 1분)

1. 이 저장소의 [`wall/`](wall/) 폴더로 이동합니다.
2. **Add file → Upload files**로 새 이미지를 올립니다. 파일 이름은 바꿀 슬롯 이름과 **똑같이** 맞춥니다 (예: `wall_e2.png`). 같은 이름이면 기존 파일을 덮어씁니다.
3. **Commit changes**를 누릅니다.
4. 1~10분 뒤(GitHub Pages 반영 시간) 월드에 새로 들어가거나, 스튜디오 컨트롤 콘솔의 분홍색 **ART** 버튼을 누르면 인스턴스 전원에게 다시 불러와집니다.

> 반영 확인: 브라우저에서 `https://zunattang.github.io/vrchatmap/` 을 열면 현재 걸린 이미지를 모두 볼 수 있습니다.

## 슬롯 위치

| 파일 | 위치 | 액자 크기 |
|---|---|---|
| `wall/wall_e1.png` | 동쪽 벽 (오른쪽), 무대 쪽 | 0.8 × 1.2 m |
| `wall/wall_e2.png` | 동쪽 벽 가운데 — **메인 포스터** | 1.0 × 1.5 m |
| `wall/wall_e3.png` | 동쪽 벽, 입구 쪽 | 0.8 × 1.2 m |
| `wall/wall_w1.png` | 서쪽 벽 (왼쪽), 채팅 보드 옆 | 0.8 × 1.2 m |
| `wall/wall_w2.png` | 서쪽 벽, 거울 뒤쪽 구석 | 0.8 × 1.2 m |

월드 안의 각 액자 오른쪽 아래에 작은 글씨로 슬롯 이름(`E1` 등)이 적혀 있습니다.

## 이미지 규격

- **비율 2:3 세로** (모든 슬롯 공통). 권장 크기 **1024 × 1536 px**. 다른 비율은 늘어나 보입니다.
- **최대 2048 × 2048 px** — 이보다 크면 VRChat이 불러오지 못합니다.
- 형식: **PNG**. 파일 이름의 확장자도 `.png`로 유지하세요 (월드는 `.png` 주소만 불러옵니다).
- 용량은 3MB 이하를 권장합니다 (방문자 로딩 시간).

## 동작 방식과 제한

- VRChat은 이미지를 **5초에 1장**씩만 불러올 수 있어, 5장이 모두 바뀌는 데 입장 후 약 30초가 걸립니다. 불러오기 전이나 실패했을 때는 월드에 내장된 기본 이미지가 보입니다.
- `github.io`는 VRChat이 기본 허용하는 주소라 방문자가 "Allow Untrusted URLs"를 켤 필요가 없습니다.
- 이미지는 각 방문자가 직접 내려받습니다. 저장소는 **공개(Public)** 상태여야 하며, 올린 이미지는 누구나 볼 수 있습니다.
- 슬롯 개수·주소를 바꾸려면 Unity 프로젝트의 `Assets/VTuberStudio/Editor/StudioBuilder.cs` (`WallSlots()`, `WallArtBaseUrl`) 수정 후 월드를 다시 업로드해야 합니다.

## 월드에 내장되는 기본 이미지 바꾸기 (Unity)

인터넷 이미지를 불러오기 전/실패 시 보이는 기본 이미지는 Unity 프로젝트의
`Assets/VTuberStudio/Art/Wall/` 폴더에 **같은 파일 이름**(`wall_e1.png` …)으로 넣으면 다음 빌드 때 반영됩니다.
이 저장소의 `wall/` 폴더를 그대로 복사해 넣으면 웹과 기본 이미지가 같아집니다. (재업로드 필요)

## 기타 파일

- [`brand/`](brand/) — 로고 엠블럼, SD 캐릭터 일러스트 원본 (월드에 쓰인 것과 동일)
- [`index.html`](index.html) — GitHub Pages 미리보기 페이지

## 처음 한 번만: GitHub Pages 켜기

1. 저장소 **Settings → General → Danger Zone → Change visibility → Public**
2. **Settings → Pages → Build and deployment → Source: Deploy from a branch**, Branch: `main` / `(root)` → **Save**
3. 몇 분 뒤 `https://zunattang.github.io/vrchatmap/` 이 열리면 완료입니다.
