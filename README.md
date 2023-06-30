# sikehuhu-pinia-persist-uni

根据[pinia-plugin-persist-uni](https://github.com/Allen-1998/pinia-plugin-persist-uni)参考写的，多谢大佬

# 使用说明

## 安装

npm i sikehuhu-pinia-persist-uni

## 配置

### Vue3

```typescript
import { createApp } from 'vue'
import { createPinia } from 'pinia'
import piniaPersist from 'sikehuhu-pinia-persist-uni'

const pinia = createPinia()
pinia.use(piniaPersist)

createApp({}).use(pinia).mount('#app')
```

### Typescript

```json
// tsconfig.json
{
  "compilerOptions": {
    "types": ["sikehuhu-pinia-persist-uni"]
  }
}
```

## 基本用法

通过在你的 stroe 中配置 persist, 将会通过 uniAppStorage 来持久化存储你的数据.

请配置 id，用于持久化存储时的 key。

```typescript
// store/user.ts
import { defineStore } from 'pinia'

export const useUserStore = defineStore('user', {
  state: () => {
    id: 'user',
    return {
      firstName: 'allen',
      lastName: 'ttk',
      accessToken: 'xxxxxxxxxxxxx',
    }
  },
  actions: {
    setToken(value: string) {
      this.accessToken = value
    },
  },
  persist: {
    enabled: true,
  },
})
```

## 参考

- [vuex-persistedstate](https://github.com/robinvdvleuten/vuex-persistedstate)
- [pinia-plugin-persist](https://github.com/Seb-L/pinia-plugin-persist)
- [pinia-plugin-persist-uni](https://github.com/Allen-1998/pinia-plugin-persist-uni)
