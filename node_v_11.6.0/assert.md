# Assert

> Stability: 2 - Stable

The assert module provides a simple set of assertion tests that can be used to test invariants.

assert模块提供一组简单的断言测试，用来测试不变量。

A strict and a legacy mode exist, while it is recommended to only use strict mode.

存在严格和传统模式，但是仅建议使用严格模式。

For more information about the used equality comparisons see MDN's guide on equality comparisons and sameness.

想要获得更多相等比较的信息，请查看MDN的相等比较和相似性的指南。

## Class: assert.AssertionError

A subclass of Error that indicates the failure of an assertion. All errors thrown by the assert module will be instances of the AssertionError class.

Error的子类, 指示断言的失败。assert模块抛出的所有错误都是AssertionError类的实例。

### new assert.AssertionError(options)

> Added in: v0.1.21

- options `<Object>`
    - message `<string>` If provided, the error message is going to be set to this value.
    - message `<string>` 如果提供，那么错误消息将会是此值。
    - actual `<any>` The actual property on the error instance is going to contain this value. Internally used for the actual error input in case e.g., assert.strictEqual() is used.
    - actual `<any>` error实例上的actual属性将包含这个值。例如，使用assert.strictEqual()，内部用来actual错误的输入。
    - expected `<any>` The expected property on the error instance is going to contain this value. Internally used for the expected error input in case e.g., assert.strictEqual() is used.
    - expected `<any>` error实例将包含此值。例如，使用assert.strictEqual()，内部用来expected错误的输入。
    - operator `<string>` The operator property on the error instance is going to contain this value. Internally used to indicate what operation was used for comparison (or what assertion function triggered the error).
    - operator `<string>` error实例将包含此值。内部用来指示对比操作，或者断言函数触发的错误。
    - stackStartFn `<Function>` If provided, the generated stack trace is going to remove all frames up to the provided function.
    - stackStartFn `<Function>` 如果提供，则由提供的函数生成堆栈跟踪。

A subclass of Error that indicates the failure of an assertion.

Error的子类，表示断言的失败。

All instances contain the built-in Error properties (message and name) and:

所有实例包含内置的Error属性（message和name）以及：

- actual `<any>` Set to the actual value in case e.g., assert.strictEqual() is used.
- actual `<any>` 在例如使用assert.strictEqual()的情况下下，设置actual值。
- expected `<any>` Set to the expected value in case e.g., assert.strictEqual() is used.
- expected `<any>` 例如使用assert.strictEqual()的情况下，设置expected值。
- generatedMessage `<boolean>` Indicates if the message was auto-generated (true) or not.
- generatedMessage `<boolean>` 指示message是否自动生成。
- code `<string>` This is always set to the string ERR_ASSERTION to indicate that the error is actually an assertion error.
- code `<string>` 始终设置ERR_ASSERTION字符串值，来指示error实际上是断言错误。
- operator `<string>` Set to the passed in operator value.
- operator `<string>` 设置为传入的运算符值。

```javascript
const assert = require('assert');

// Generate an AssertionError to compare the error message later:
const { message } = new assert.AssertionError({
  actual: 1,
  expected: 2,
  operator: 'strictEqual'
});

// Verify error output:
try {
  assert.strictEqual(1, 2);
} catch (err) {
  assert(err instanceof assert.AssertionError);
  assert.strictEqual(err.message, message);
  assert.strictEqual(err.name, 'AssertionError [ERR_ASSERTION]');
  assert.strictEqual(err.actual, 1);
  assert.strictEqual(err.expected, 2);
  assert.strictEqual(err.code, 'ERR_ASSERTION');
  assert.strictEqual(err.operator, 'strictEqual');
  assert.strictEqual(err.generatedMessage, true);
}
```


