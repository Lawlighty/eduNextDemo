This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/import?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.


## 使用antd框架需要
- cnpm install @zeit/next-css  项目不支持外部css
- 然后根目录下，写一个next.config.js
  ```bash
    const withCss = require('@zeit/next-css')

    if(typeof require !== 'undefined'){
        require.extensions['.css']=file=>{}
    }

    module.exports = withCss({})
```
- 根目录创建 .babelrc
  ```bash
    {
  "presets": ["next/babel"], // Next.js的配置文件，相当于继承了它本身的所有配置
  "plugins": [
    // 增加新的插件，这个插件就是让antd可以按需引入，包括css
    [
      "import",
      {
        "libraryName": "antd",
        "style": "css" // 引入css
      }
    ]
  ]
}

  ```

- 根目录创建 next.config.js
  ```bash
  const withCss = require("@zeit/next-css");

    if (typeof require !== "undefined") {
    require.extensions[".css"] = (file) => {};
    }

    module.exports = withCss({});

  ```