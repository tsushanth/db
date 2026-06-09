---
id: or
title: or
---

# Function: or()

## Call Signature

```ts
function or(left, right): BasicExpression<boolean>;
```

Defined in: [packages/db/src/query/builder/functions.ts:244](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L244)

### Parameters

#### left

`ExpressionLike`

#### right

`ExpressionLike`

### Returns

[`BasicExpression`](../@tanstack/namespaces/IR/type-aliases/BasicExpression.md)\<`boolean`\>

## Call Signature

```ts
function or(
   left, 
   right, ...
rest): BasicExpression<boolean>;
```

Defined in: [packages/db/src/query/builder/functions.ts:248](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L248)

### Parameters

#### left

`ExpressionLike`

#### right

`ExpressionLike`

#### rest

...`ExpressionLike`[]

### Returns

[`BasicExpression`](../@tanstack/namespaces/IR/type-aliases/BasicExpression.md)\<`boolean`\>
