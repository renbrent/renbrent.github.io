# Tasks: Portfolio Site Implementation

**Created**: 2026-01-15  
**Project**: Brent Basiano Portfolio Site (renbrent.github.io)  
**Status**: Ready for execution

## Format: `- [ ] [ID] [P?] Description with file path`

- **[P]**: Can run in parallel (different files, no dependencies)
- Include exact file paths and commands in descriptions

---

## Phase 1: Theme Installation & Setup

**Purpose**: Install Hugo theme and verify local development environment

 - [ ] T001 Install Hugo (Arch Linux): `sudo pacman -Syu && sudo pacman -S hugo`
 - [ ] T002 Verify Hugo installation (Extended): `hugo version` (look for `extended` in the version output; target v0.121.0 or later)
 - [X] T003 Initialize git submodule for hugo-profile theme: `git submodule add https://github.com/gurusabarish/hugo-profile.git themes/hugo-profile`
 - [X] T004 Update git submodule: `git submodule update --init --recursive`
- [ ] T005 Test local Hugo server: `hugo server -D` and verify site loads at http://localhost:1313
 - [X] T005 Test local Hugo server: `hugo server -D` and verify site loads at http://localhost:1313

**Checkpoint**: Hugo theme installed, local server running successfully

---

## Phase 2: Content Customization

**Purpose**: Personalize site content with your professional information

- [ ] T006 Update email address in hugo.toml at params.contact.email (line ~138)
 - [X] T007 [P] Update GitHub URL in hugo.toml at params.footer.socialNetworks.icons (line ~143) to https://github.com/renbrent
- [ ] T008 [P] Update LinkedIn URL in hugo.toml at params.footer.socialNetworks.icons (line ~146) with your LinkedIn profile
- [ ] T009 [P] Update Twitter/X URL in hugo.toml at params.footer.socialNetworks.icons (line ~149) or remove if not applicable
- [ ] T010 Customize hero content in hugo.toml at params.hero.content (line ~30) with your professional summary
- [ ] T011 Update about section in hugo.toml at params.about.content (line ~47) with your background and expertise
- [ ] T012 [P] Update skills list in hugo.toml at params.about.skills.items (line ~53) with your actual technical skills
- [ ] T013 Update experience section in hugo.toml starting at params.experience.items (line ~68) with your actual work history
- [ ] T014 Update education section in hugo.toml at params.education.items (line ~93) with your actual educational background
- [ ] T015 Update projects section in hugo.toml starting at params.projects.items (line ~109) with your actual projects
- [ ] T016 For each project in hugo.toml, update GitHub URLs and demo links with real repository links

**Checkpoint**: All placeholder content replaced with real professional information

---

## Phase 3: Asset Preparation & Upload

**Purpose**: Add visual assets (photos, resume, project images)

- [ ] T017 Prepare profile photo: resize to 400x400px, optimize to <200KB, save as WebP or JPG
- [ ] T018 Add profile photo to static/images/profile.jpg
- [ ] T019 Create or update favicon: create 32x32px icon and save to static/images/favicon.ico
- [ ] T020 [P] Prepare resume PDF: ensure up-to-date, save to static/files/resume.pdf
- [ ] T021 [P] Prepare project screenshot for project 1: resize to 1200x630px, optimize to <200KB
- [ ] T022 [P] Add project 1 screenshot to static/images/projects/ (name matching hugo.toml reference)
- [ ] T023 [P] Prepare project screenshot for project 2: resize to 1200x630px, optimize to <200KB
- [ ] T024 [P] Add project 2 screenshot to static/images/projects/ (name matching hugo.toml reference)
- [ ] T025 [P] Prepare project screenshot for project 3: resize to 1200x630px, optimize to <200KB
- [ ] T026 [P] Add project 3 screenshot to static/images/projects/ (name matching hugo.toml reference)
- [ ] T027 Verify all image paths in hugo.toml match actual filenames in static/images/

**Checkpoint**: All images added, paths verified, file sizes optimized per constitution (<200KB each)

---

## Phase 4: Local Testing & Quality Assurance

**Purpose**: Verify site works correctly before deployment

- [ ] T028 Start Hugo development server: `hugo server -D`
- [ ] T029 Test homepage loads correctly at http://localhost:1313
- [ ] T030 Verify hero section displays with correct name, title, and profile photo
- [ ] T031 Click "Resume" button and verify PDF downloads from /files/resume.pdf
- [ ] T032 Click "Projects" button and verify smooth scroll to projects section
- [ ] T033 Verify about section displays with profile photo and skills list
- [ ] T034 Verify experience section shows all job entries with correct formatting
- [ ] T035 Verify education section displays correctly
- [ ] T036 Test each project card: verify image loads, badges display, and links work
- [ ] T037 Test GitHub links open correct repositories in new tabs
- [ ] T038 Test demo links (if applicable) open correct live sites
- [ ] T039 Test contact section displays email with "Email Me" button
- [ ] T040 Verify footer social links (GitHub, LinkedIn, Twitter) work correctly
- [ ] T041 Test responsive design: resize browser to 320px, 768px, 1024px, 1920px widths
- [ ] T042 Test mobile navigation menu (hamburger icon) if theme includes it
- [ ] T043 Test keyboard navigation: Tab through all links and buttons
- [ ] T044 Verify no console errors in browser developer tools (F12)

**Checkpoint**: Site fully functional locally with no errors

---

## Phase 5: Performance & Accessibility Validation

**Purpose**: Ensure site meets constitution performance standards

- [ ] T045 Build production site: `hugo --minify --gc`
- [ ] T046 Check bundle sizes: `ls -lh public/` and verify total page weight <500KB
- [ ] T047 Run Lighthouse audit on local build: Open http://localhost:1313 in Chrome Incognito, open DevTools (F12), run Lighthouse
- [ ] T048 Verify Lighthouse Performance score ≥90
- [ ] T049 Verify Lighthouse Accessibility score ≥95
- [ ] T050 Verify Lighthouse Best Practices score ≥95
- [ ] T051 Verify Lighthouse SEO score ≥95
- [ ] T052 Check Core Web Vitals: LCP <2.5s, FID <100ms, CLS <0.1
- [ ] T053 Fix any accessibility issues reported by Lighthouse (color contrast, alt text, ARIA labels)
- [ ] T054 Optimize any oversized images if bundle exceeds limits
- [ ] T055 Re-run Lighthouse after fixes to confirm all scores meet thresholds

**Checkpoint**: All performance and accessibility targets met per constitution

---

## Phase 6: Git & Deployment Setup

**Purpose**: Prepare repository and configure GitHub Pages

 - [X] T056 Review changes: `git status` to see all modified and new files
 - [X] T057 Stage Hugo configuration: `git add hugo.toml`
 - [X] T058 Stage GitHub Actions workflow: `git add .github/workflows/deploy.yml`
 - [X] T059 Stage static assets: `git add static/`
 - [X] T060 Stage archetypes: `git add archetypes/`
 - [X] T061 Stage README and gitignore: `git add README.md .gitignore`
 - [X] T062 Stage theme submodule: `git add .gitmodules themes/`
 - [ ] T063 Verify public/ directory is NOT staged (should be in .gitignore): `git status | grep public/` should return nothing
 - [X] T064 Commit initial portfolio site: `git commit -m "feat: initial Hugo portfolio site with hugo-profile theme"`
 - [ ] T065 Push to GitHub: `git remote add origin https://github.com/renbrent/renbrent.github.io.git` then `git push -u origin master`
- [ ] T066 Go to GitHub repository Settings > Pages
- [ ] T067 Set Pages source to "GitHub Actions" (not branch)
- [ ] T068 Wait for GitHub Actions workflow to complete (check Actions tab)
- [ ] T069 Verify deployment succeeded in Actions tab (green checkmark)
- [ ] T070 Visit https://renbrent.github.io and verify site loads

**Checkpoint**: Site successfully deployed to GitHub Pages

---

## Phase 7: Post-Deployment Validation

**Purpose**: Verify production site meets all requirements

- [ ] T071 Open https://renbrent.github.io in multiple browsers (Chrome, Firefox, Safari, Edge)
- [ ] T072 Test all navigation links work on production site
- [ ] T073 Verify resume PDF downloads from production site
- [ ] T074 Test all external links (GitHub, LinkedIn, project demos) open correctly
- [ ] T075 Test site on mobile device (iPhone/Android) or browser mobile emulation
- [ ] T076 Run Lighthouse audit on production URL (https://renbrent.github.io)
- [ ] T077 Verify production Lighthouse scores meet constitution thresholds (≥90/95/95/95)
- [ ] T078 Check Google Search Console submission (optional): https://search.google.com/search-console
- [ ] T079 Verify site appears correctly in social media preview (share link on LinkedIn/Twitter to test)
- [ ] T080 Test site on slow 3G network (Chrome DevTools > Network > Slow 3G) to verify LCP <2.5s

**Checkpoint**: Production site fully validated and ready for recruiter traffic

---

## Phase 8: Documentation & Maintenance

**Purpose**: Document setup and plan for ongoing updates

- [ ] T081 Update README.md with your actual contact information (email, GitHub, LinkedIn)
- [ ] T082 Document any custom configuration in README.md if you deviated from defaults
- [ ] T083 Create CHANGELOG.md (optional): document initial v1.0.0 release
- [ ] T084 Add LICENSE file if open sourcing (MIT License recommended)
- [ ] T085 Set up calendar reminder to update portfolio quarterly (add new projects, refresh resume)
- [ ] T086 Bookmark Lighthouse CI URL for periodic performance checks
- [ ] T087 Share portfolio URL with friends/colleagues for feedback
- [ ] T088 Add portfolio URL to GitHub profile README and LinkedIn profile

**Checkpoint**: Portfolio site complete, documented, and ready for job search 🎉

---

## Parallel Execution Opportunities

Tasks marked with [P] can be executed in parallel within their phase:

**Phase 2** (Content): T007-T009, T012 can be edited simultaneously in different config sections
**Phase 3** (Assets): T020-T026 - all image preparation and uploads are independent
**Phase 6** (Git): T057-T062 can be staged together: `git add hugo.toml .github/workflows/ static/ archetypes/ README.md .gitignore .gitmodules themes/`

## Dependencies

- **Phase 2** depends on Phase 1 completion (theme must be installed)
- **Phase 3** depends on Phase 2 (content must reference correct asset paths)
- **Phase 4** depends on Phase 3 (assets must exist for testing)
- **Phase 5** depends on Phase 4 (basic functionality must work first)
- **Phase 6** depends on Phase 5 (must pass quality gates before deployment)
- **Phase 7** depends on Phase 6 (deployment must complete)
- **Phase 8** depends on Phase 7 (production validation before documentation)

## Implementation Strategy

1. **MVP First**: Complete Phases 1-4 for a working local site
2. **Quality Gates**: Phase 5 must pass before deployment
3. **Deploy**: Phase 6 gets site live
4. **Polish**: Phases 7-8 ensure production quality and long-term maintenance

## Estimated Timeline

- Phase 1: 15 minutes (theme installation)
- Phase 2: 1-2 hours (content customization)
- Phase 3: 1-2 hours (asset preparation)
- Phase 4: 30 minutes (local testing)
- Phase 5: 30 minutes (performance validation)
- Phase 6: 15 minutes (deployment)
- Phase 7: 30 minutes (production testing)
- Phase 8: 30 minutes (documentation)

**Total**: 4-6 hours for complete portfolio site launch

---

**Generated**: 2026-01-15  
**Total Tasks**: 88  
**Parallel Tasks**: 12  
**Constitution Compliance**: ✓ Performance standards, ✓ Testing requirements, ✓ UX consistency, ✓ Code quality
