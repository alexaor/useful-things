# Readme
## General notes
Collection of changes that converts a CRA app to using Vite
https://github.com/vitejs/vite/issues/1652#issuecomment-765875146

## Other important steps
- Remove all references to %PUBLIC_URL% from index.html
- Move index.html to project root
- Add `<script type="module" src="/src/index.tsx"></script>` to index.html right before closing the `</body>` tag

## Depdendency specific hiccups
react-markdown had to be upgraded major version from 4 to 8 and instead of `source` 
prop you wrap it around some child. Meaning we move from this
```
<ReactMarkdown source={appNotification.message}/>
```
to this
```
 <ReactMarkdown>
    {appNotification.message}
  </ReactMarkdown>
```
- @types/intl had to be added