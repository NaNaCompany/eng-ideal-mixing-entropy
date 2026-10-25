# 이상기체 혼합 엔트로피 계산기

처음에 같은 온도와 압력으로 분리되어 있던 서로 다른 이상기체를 혼합할 때의 엔트로피 증가를 구합니다.

- ID: E154
- App: https://nanalab.kr/eng-ideal-mixing-entropy/
- Repository: https://github.com/NaNaCompany/eng-ideal-mixing-entropy
- Formula: ΔSmix = −R Σ[nᵢ ln(xᵢ)]; xᵢ = nᵢ/Σnᵢ; lim(nᵢ→0⁺) nᵢ ln(nᵢ/Σnⱼ) = 0

## Model and data

각 행은 서로 다른 화학종 하나를 뜻합니다. 같은 기체를 여러 행에 나눠 입력하면 안 됩니다. 모든 기체의 초기 온도와 압력이 같고, 반응·상변화·비이상성 없이 혼합한다고 가정합니다. 0 mol 행은 제외되며 적어도 한 행은 양수여야 합니다. 기체가 한 종류만 남으면 ΔS=0입니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
