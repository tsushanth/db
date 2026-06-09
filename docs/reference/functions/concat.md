---
id: concat
title: concat
---

# Function: concat()

## Call Signature

```ts
function concat<T>(arg): ConcatToArrayWrapper<T>;
```

Defined in: [packages/db/src/query/builder/functions.ts:320](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L320)

### Type Parameters

#### T

`T` *extends* `StringifiableScalar`

### Parameters

#### arg

`ToArrayWrapper`\<`T`\>

### Returns

`ConcatToArrayWrapper`\<`T`\>

## Call Signature

```ts
function concat(...args): BasicExpression<string>;
```

Defined in: [packages/db/src/query/builder/functions.ts:323](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L323)

### Parameters

#### args

...`ExpressionLike`[]

### Returns

[`BasicExpression`](../@tanstack/namespaces/IR/type-aliases/BasicExpression.md)\<`string`\>
