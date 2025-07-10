1. 避免open一个重复的窗口（如客服面板）
```javascript
openOrSwitchToTab(`xxx`, 'customerService');

function openOrSwitchToTab(url: string, target: string) { // 尝试获取已经打开的窗口
  const existingTab = window.open('', target);
  // 检查窗口是否已经存在
  if (existingTab?.location.href !== 'about:blank') {
  // 如果窗口已经存在，则切换到该窗口
    existingTab?.focus();
  } else { // 如果窗口不存在，则打开新的窗口
    existingTab.location.href = url;
  }
}
```
