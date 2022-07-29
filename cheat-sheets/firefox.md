# about:config
toolkit.legacyUserProfileCustomizations.stylesheets = true

# about:profiles
Enable userChrome.css support in Fx v69+

1. Open about:support
2. Click on "Profile Folder" -> "Open Folder"
3. Create a sub-folder named "chrome"
4. Create a file named "userChrome.css"

# hide tab bar when using sidebery/tree style tabe
```css
#tabbrowser-tabs {
  visibility: collapse !important;
}
```

# Restart Firefox
about:profiles
