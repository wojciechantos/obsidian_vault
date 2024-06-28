
Example:

```js
import { Theme } from '@/features/theme/themeSlice';  
  
export function applyTheme (theme) {  
    const root = window.document.documentElement;  
    root.classList.remove('light', 'dark');  
  
    if (theme === 'system') {  
        const systemTheme =  
            window
            // check user system preference
            .matchMedia('(prefers-color-scheme:dark)') 
            .matches ? 'dark' : 'light';  
        root.classList.add(systemTheme);  
  
        return;  
    }  
}
```