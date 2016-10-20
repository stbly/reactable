# Reactable Cacheable

Reactable Cacheable is a fork of Glittershark's awesome [Reactable](https://github.com/glittershark/reactable) that adds caching of data and rows. I found that, as I started building custom table cells that contained other React components, sorting tables became a slow process, as the rows and their cells were being rebuilt on each sort. Reactable Cacheable saves and indexes the rows after it creates them so that, when no data in the table has changed, React can just use the existing row component instead of creating a whole new one. This fills a pretty niche need, as plain text cells render extremely fast with the parent Reactable class, but it does help with sorting speeds when using components in cells. 

## Installation

```sh
npm install [--save] reactable-cacheable
```

## Usage

For detailed usage of Reactable, you'll want to check out the documentation [here](https://github.com/glittershark/reactable#usage). Reactable Cacheable uses the exact same syntax; you're just importing a different class. See below:

```jsx
import Table from 'reactable-cacheable'
ReactDOM.render(
    <CacheableTable className="table" data={[
        { foo: bar },
        { foo: baz },
        { foo: etc },
    ]} />,
    document.getElementById('table')
);
```

If you want to disable caching altogether, simply add the `noCaching` property to the Table component:

```jsx
import Table from 'reactable-cacheable'
ReactDOM.render(
    <CacheableTable className="table" noCaching data={[
        { foo: bar },
        { foo: baz },
        { foo: etc },
    ]} />,
    document.getElementById('table')
);
```

Be sure to check out the aforementioned documentation; Reactable allows you some pretty nice customization for sorting and filtering. 