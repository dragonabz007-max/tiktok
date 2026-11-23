TikTok Review Studio - Build IPA tren Codemagic - Huong dan chi tiet

BUOC 1: Push len GitHub
1. Tao repo moi tren GitHub, vd: tiktok-review-studio
2. Giai nen file zip nay, push toan bo file len repo (codemagic.yaml nam o thu muc goc)
3. Chay: git init, git add ., git commit -m init, git remote add origin <link repo>, git push -u origin main

BUOC 2: Ket noi Codemagic
1. Vao codemagic.io > Sign up bang GitHub > Add application > Chon repo vua push
2. Codemagic tu doc file codemagic.yaml, hien workflow ios-ipa

BUOC 3: Cai dat ky so (quan trong de ra .ipa cai duoc)
1. Trong Codemagic > Teams > Code signing identities > Them Apple Developer Account (can Apple ID + App Specific Password)
2. Hoac vao Application > Code signing > iOS code signing > Add certificate (.p12) + Provisioning profile
3. Sua file ios/ExportOptions.plist: thay YOUR_TEAM_ID bang Team ID cua ban (lay trong developer.apple.com > Membership)
4. Neu chua co Provisioning, chon Automatic signing trong Codemagic, no tu tao cho ban

BUOC 4: Build
1. Bam Start new build > Chon workflow ios-ipa > Start build
2. Doi 5-10 phut, vao Artifacts > Tai file .ipa ve
3. Cai .ipa: dung AltStore / Sideloadly / Apple Configurator, hoac gui link Codemagic cho tester cai qua TestFlight

LUU Y:
- Neu chua co tai khoan Apple Developer tra phi (99$/nam), ban van build duoc ban Development / Ad Hoc de cai len may cua ban (toi da 100 may, can them UDID iPhone vao Provisioning)
- Muon dang App Store / TestFlight, can tai khoan Developer tra phi.
- File codemagic.yaml da cau hinh san: flutter stable, xcode latest, build ipa release.
