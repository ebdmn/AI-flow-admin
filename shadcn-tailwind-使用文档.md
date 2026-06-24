# shadcn + Tailwind 使用速查（只讲怎么用）

> 场景：日常写页面，直接查写法。只保留常用示例。

---

## 1. 固定值与任意值

```tsx
<div className="w-64 h-40 p-4">固定宽高和内边距</div>
<div className="w-[320px] h-[180px]">任意值</div>
<div className="top-[72px] left-[20px]">任意定位值</div>
<div className="max-w-[860px]">常见内容最大宽度</div>
<div className="min-h-[calc(100vh-64px)]">减去头部后的最小高度</div>
<div className="rounded-[10px]">任意圆角</div>
```

---

## 2. 长宽与定位

```tsx
<div className="w-full max-w-md h-56">宽高</div>
<div className="relative">
  <div className="absolute top-2 right-2">绝对定位</div>
</div>
<div className="fixed bottom-4 right-4 z-50">固定定位悬浮按钮</div>
<div className="sticky top-0 z-40">吸顶栏</div>
<div className="inset-0 absolute">铺满父容器</div>
<div className="left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 absolute">居中定位</div>
```

```tsx
<div className="relative h-48 rounded-lg border border-line">
  <span className="absolute left-3 top-3 rounded bg-background px-2 py-1 text-xs">左上角标签</span>
  <button className="absolute right-3 bottom-3 rounded-md bg-action px-3 py-1.5 text-primary-foreground">
    操作
  </button>
</div>
```

---

## 3. 边距、边框、圆角

```tsx
<div className="m-4 p-4">外边距 + 内边距</div>
<div className="px-4 py-2">横向/纵向内边距</div>
<div className="border border-border">默认边框</div>
<div className="border-b border-line">底边框</div>
<div className="rounded-md">圆角</div>
<div className="rounded-full border border-border">胶囊</div>
<div className="divide-y divide-line">子项分割线</div>
<div className="ring-1 ring-ring/40">环形边框</div>
```

```tsx
<div className="rounded-xl border border-line bg-surface p-4 shadow-sm">
  <h3 className="mb-2 text-sm font-semibold">卡片标题</h3>
  <p className="text-sm text-fg-muted">卡片说明文案</p>
</div>
```

---

## 4. 布局（Flex / Grid）

```tsx
<div className="flex items-center justify-between gap-3">Flex 水平布局</div>
<div className="flex flex-col gap-2">Flex 垂直布局</div>
<div className="grid grid-cols-2 gap-4">2 列网格</div>
<div className="grid grid-cols-12 gap-4">
  <aside className="col-span-3">侧栏</aside>
  <main className="col-span-9">主内容</main>
</div>
<div className="flex flex-wrap gap-2">自动换行</div>
<div className="grid auto-rows-min gap-3">自动行高网格</div>
```

```tsx
<div className="grid gap-4 sm:grid-cols-2 lg:grid-cols-4">
  <div className="rounded-lg border border-line bg-surface p-3">统计卡片 A</div>
  <div className="rounded-lg border border-line bg-surface p-3">统计卡片 B</div>
  <div className="rounded-lg border border-line bg-surface p-3">统计卡片 C</div>
  <div className="rounded-lg border border-line bg-surface p-3">统计卡片 D</div>
</div>
```

---

## 5. 浮动与清除浮动

```tsx
<img className="float-left mr-3 mb-2 w-24 h-24" src="..." alt="" />
<p>文字环绕图片</p>
<div className="clear-both" />
```

> 新页面布局优先用 `flex/grid`，`float` 主要用于图文环绕。

---

## 6. 溢出、滚动、截断

```tsx
<div className="max-h-80 overflow-y-auto">纵向滚动区域</div>
<div className="overflow-x-auto">
  <table className="min-w-[720px]">宽表格横向滚动</table>
</div>
<p className="truncate">单行省略...</p>
<p className="line-clamp-2">两行省略，两行省略，两行省略，两行省略...</p>
<div className="whitespace-nowrap">不换行</div>
```

---

## 7. 颜色、字号、字重

```tsx
<div className="bg-background text-foreground">语义前景/背景</div>
<div className="bg-page text-fg">项目别名</div>
<div className="bg-primary text-primary-foreground">主按钮</div>
<p className="text-sm">小号文字</p>
<p className="text-base font-medium">中号 + 中等字重</p>
<p className="text-lg font-semibold">大号 + 半粗</p>
<p className="text-fg-muted">次要文字</p>
<p className="text-fg-subtle">弱提示文字</p>
```

```tsx
<h1 className="text-2xl font-semibold tracking-tight">页面标题</h1>
<p className="mt-1 text-sm leading-6 text-fg-muted">描述文本用于解释当前页面操作。</p>
```

---

## 8. 常用状态写法

```tsx
<button className="bg-action hover:bg-action-hover active:scale-95 transition">
  保存
</button>

<input className="border border-border focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring" />

<button className="disabled:opacity-50 disabled:cursor-not-allowed" disabled>
  禁用按钮
</button>

<div className="border border-transparent hover:border-line transition-colors">悬浮出现边框</div>
<div className="data-[state=active]:bg-background">data-state 状态样式</div>
```

```tsx
<button className="rounded-md border border-line bg-background px-3 py-1.5 text-sm hover:bg-surface-muted">
  次按钮
</button>
<button className="rounded-md bg-destructive px-3 py-1.5 text-sm text-white hover:opacity-90">
  危险操作
</button>
```

---

## 9. 表单常用写法

```tsx
<div className="grid gap-4 sm:grid-cols-2">
  <label className="grid gap-2">
    <span className="text-sm text-fg-muted">用户名</span>
    <input className="h-10 rounded-md border border-border bg-background px-3 outline-none focus-visible:ring-2 focus-visible:ring-ring" />
  </label>

  <label className="grid gap-2">
    <span className="text-sm text-fg-muted">邮箱</span>
    <input className="h-10 rounded-md border border-border bg-background px-3 outline-none focus-visible:ring-2 focus-visible:ring-ring" />
  </label>
</div>

<textarea className="mt-4 min-h-28 w-full rounded-md border border-border bg-background p-3 outline-none focus-visible:ring-2 focus-visible:ring-ring" />
```

---

## 10. 列表与表格常用写法

```tsx
<ul className="divide-y divide-line rounded-lg border border-line bg-surface">
  <li className="flex items-center justify-between px-4 py-3">
    <span className="text-sm">列表项 A</span>
    <button className="text-sm text-fg-muted hover:text-fg">详情</button>
  </li>
  <li className="flex items-center justify-between px-4 py-3">
    <span className="text-sm">列表项 B</span>
    <button className="text-sm text-fg-muted hover:text-fg">详情</button>
  </li>
</ul>
```

```tsx
<div className="overflow-x-auto rounded-lg border border-line bg-surface">
  <table className="min-w-full text-sm">
    <thead className="bg-surface-muted text-fg-muted">
      <tr>
        <th className="px-4 py-2 text-left">姓名</th>
        <th className="px-4 py-2 text-left">角色</th>
        <th className="px-4 py-2 text-right">操作</th>
      </tr>
    </thead>
    <tbody className="divide-y divide-line">
      <tr>
        <td className="px-4 py-3">张三</td>
        <td className="px-4 py-3">管理员</td>
        <td className="px-4 py-3 text-right text-fg-muted">编辑</td>
      </tr>
    </tbody>
  </table>
</div>
```

---

## 11. 常用语义 class 速查（你们项目可直接用）

### 11.1 shadcn 语义入口（推荐组件场景）

| Tailwind class | 主题变量 | 语义变量 | 项目 token（当前映射） |
|---|---|---|---|
| `bg-background` | `--color-background` | `--background` | `--color-bg-page` |
| `text-foreground` | `--color-foreground` | `--foreground` | `--color-text-primary` |
| `border-border` | `--color-border` | `--border` | `--color-border-default` |
| `bg-card` | `--color-card` | `--card` | `--color-bg-card` |
| `text-card-foreground` | `--color-card-foreground` | `--card-foreground` | `--color-text-primary` |
| `bg-popover` | `--color-popover` | `--popover` | `--color-bg-elevated` |
| `bg-primary` | `--color-primary` | `--primary` | `--color-brand-600` |
| `text-primary-foreground` | `--color-primary-foreground` | `--primary-foreground` | `#ffffff` |
| `bg-secondary` | `--color-secondary` | `--secondary` | `--color-bg-muted` |
| `text-muted-foreground` | `--color-muted-foreground` | `--muted-foreground` | `--color-text-secondary` |

### 11.2 项目别名入口（推荐业务语义场景）

| Tailwind class | 来源变量 | 对应 token |
|---|---|---|
| `bg-page` | `--color-page` | `--color-bg-page` |
| `bg-surface` | `--color-surface` | `--color-bg-card` |
| `bg-elevated` | `--color-elevated` | `--color-bg-elevated` |
| `text-fg` | `--color-fg` | `--color-text-primary` |
| `text-fg-muted` | `--color-fg-muted` | `--color-text-secondary` |
| `border-line` | `--color-line` | `--color-border-default` |
| `bg-action` | `--color-action` | `--color-primary` |
| `bg-action-hover` | `--color-action-hover` | `--color-primary-hover` |

---

## 12. 页面骨架示例（可直接抄）

```tsx
<div className="min-h-screen bg-page text-fg">
  <header className="sticky top-0 z-40 border-b border-line bg-background px-4 py-3">
    <div className="flex items-center justify-between">
      <h1 className="text-base font-semibold">页面标题</h1>
      <button className="rounded-md bg-action px-3 py-1.5 text-primary-foreground hover:bg-action-hover">
        新建
      </button>
    </div>
  </header>

  <main className="grid grid-cols-12 gap-4 p-4">
    <aside className="col-span-3 rounded-lg border border-line bg-surface p-4">侧栏</aside>
    <section className="col-span-9 rounded-lg border border-line bg-surface p-4">主内容</section>
  </main>
</div>
```

```tsx
<div className="mx-auto w-full max-w-7xl p-4 sm:p-6 lg:p-8">
  <div className="mb-4 flex flex-wrap items-center justify-between gap-3">
    <div>
      <h2 className="text-xl font-semibold">用户列表</h2>
      <p className="text-sm text-fg-muted">共 124 人</p>
    </div>
    <div className="flex items-center gap-2">
      <input className="h-9 rounded-md border border-border bg-background px-3 text-sm" placeholder="搜索用户" />
      <button className="h-9 rounded-md bg-action px-3 text-sm text-primary-foreground hover:bg-action-hover">搜索</button>
    </div>
  </div>

  <div className="rounded-lg border border-line bg-surface p-4">内容区域</div>
</div>
```
