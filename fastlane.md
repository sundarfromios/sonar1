# using sonar-objective-c with fastlane

If, like me, you want to use fastlane instead of run-sonar.sh, you could use this lane.

```
scan(
     scheme: "your_scheme",
     clean: true,
     code_coverage: true,
     output_directory: "sonar-reports",
     output_types: "junit,json-compilation-database",
     buildlog_path: "sonar-reports",
     derived_data_path: "sonar-reports",
     use_clang_report_name: true,
     custom_report_file_name: "TEST-report.xml",
     xcargs: "ONLY_ACTIVE_ARCH=YES"
   )
   slather(
     simple_output: true,
     cobertura_xml: true,
     output_directory: "sonar-reports",
     proj: "your.xcodeproj",
     scheme: "your_scheme",
     build_directory: "sonar-reports",
     ignore: ["../../../Applications/Xcode.app/*", "../../../../../Applications/Xcode.app/*", "Vendors/*", "Crashlytics.framework/*"]
   )
   oclint(
     compile_commands: "sonar-reports/compile_commands.json",
     report_type: 'pmd',
     select_regex: /your_src_folder/,
     max_priority_1: 10,
     max_priority_2: 1000,
     max_priority_3: 4000,
     enable_clang_static_analyzer: false,
     allow_duplicated_violations: false,
     list_enabled_rules: true,
     report_path: "sonar-reports/oclint.xml"
   )
   sonar
```