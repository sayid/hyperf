# v2.2.8 - TBD

## Fixed

- [#4028](https://github.com/hyperf/hyperf/pull/4028) Fixed the success rate calculation in grafana dashboard.
- [#4030](https://github.com/hyperf/hyperf/pull/4030) Fixed bug that async-queue broken caused by uncompressing model failed.

## Added

- [#4013](https://github.com/hyperf/hyperf/pull/4013) Support `sameSite=None` when return response with cookies.
- [#4017](https://github.com/hyperf/hyperf/pull/4017) Added `Macroable` into `Hyperf\Utils\Collection`.
- [#4021](https://github.com/hyperf/hyperf/pull/4021) Added argument `$attempts` into `$callback` when using function `retry()`.
- [#4040](https://github.com/hyperf/hyperf/pull/4040) Added method `ConsumerDelayedMessageTrait::getDeadLetterExchange()` which used to rewrite `x-dead-letter-exchange` by yourself.

## Removed

- [#4017](https://github.com/hyperf/hyperf/pull/4017) Removed `Macroable` from `Hyperf\Database\Model\Collection` because it already exists in `Hyperf\Utils\Collection`.

# v2.2.7 - 2021-09-06

# Fixed

- [#3997](https://github.com/hyperf/hyperf/pull/3997) Fixed unexpected termination of nats consumer after timeout.
- [#3998](https://github.com/hyperf/hyperf/pull/3998) Fixed bug that `apollo` does not support `https`.

## Optimized

- [#4009](https://github.com/hyperf/hyperf/pull/4009) Optimized method `MethodDefinitionCollector::getOrParse()` to avoid deprecated in PHP8.

## Added

- [#4002](https://github.com/hyperf/hyperf/pull/4002) [#4012](https://github.com/hyperf/hyperf/pull/4012) Support method `FormRequest::scene()` which used to rewrite different rules according to different scenes.
- [#4011](https://github.com/hyperf/hyperf/pull/4011) Added some methods for `Hyperf\Utils\Str`.

# v2.2.6 - 2021-08-30

## Fixed

- [#3969](https://github.com/hyperf/hyperf/pull/3969) Fixed type error when using `Hyperf\Validation\Rules\Unique::__toString()` in PHP8.
- [#3979](https://github.com/hyperf/hyperf/pull/3979) Fixed bug that timeout property does not work in circuit breaker.
- [#3986](https://github.com/hyperf/hyperf/pull/3986) Fixed OSS hook failed when using `SWOOLE_HOOK_NATIVE_CURL`.

## Added

- [#3987](https://github.com/hyperf/hyperf/pull/3987) Support delayed message exchange for AMQP.
- [#3989](https://github.com/hyperf/hyperf/pull/3989) [#3992](https://github.com/hyperf/hyperf/pull/3992) Added option `command` which used to define your own start command.

# v2.2.5 - 2021-08-23

## Fixed

- [#3959](https://github.com/hyperf/hyperf/pull/3959) Fixed validate rule `date` does not work as expected when the value isn't string.
- [#3960](https://github.com/hyperf/hyperf/pull/3960) Fixed bug that crontab cannot be closed safely in coroutine style server.

## Added

- [code-generator](https://github.com/hyperf/code-generator) Added `code-generator` which used to regenerate classes with `Attributes` instead of `Doctrine Annotations`.

## Optimized

- [#3957](https://github.com/hyperf/hyperf/pull/3957) Support generate the type of getAttribute with `@return` for command `gen:model`.

# v2.2.4 - 2021-08-16

## Fixed

- [#3925](https://github.com/hyperf/hyperf/pull/3925) Fixed bug that heartbeat failed caused by nacos light beat enabled.
- [#3926](https://github.com/hyperf/hyperf/pull/3926) Fixed bug that the config of `config_center.drivers.nacos.client` does not work.

## Added

- [#3924](https://github.com/hyperf/hyperf/pull/3924) Added health check parameters for consul service register.
- [#3932](https://github.com/hyperf/hyperf/pull/3932) Support requeue the message when return `NACK` for `AMQP` consumer.
- [#3941](https://github.com/hyperf/hyperf/pull/3941) Support service register for `rpc-multiplex`.
- [#3947](https://github.com/hyperf/hyperf/pull/3947) Added method `Str::mask` which used to replace chars from a string by a given char.

## Optimized

- [#3944](https://github.com/hyperf/hyperf/pull/3944) Encapsulated the code for reading aspect meta properties.

# v2.2.3 - 2021-08-09

## Fixed

- [#3897](https://github.com/hyperf/hyperf/pull/3897) Fixed bug that nacos instance will be registered more than once, because heartbeat failed caused by light beat enabled.
- [#3905](https://github.com/hyperf/hyperf/pull/3905) Fixed null pointer exception when closing AMQPConnection.
- [#3906](https://github.com/hyperf/hyperf/pull/3906) Fixed bug that close connection failed caused by wait channels flushed.
- [#3908](https://github.com/hyperf/hyperf/pull/3908) Fixed bug that the process couldn't be restarted caused by loop which using `CoordinatorManager`.

# v2.2.2 - 2021-08-03

## Fixed

- [#3872](https://github.com/hyperf/hyperf/pull/3872) [#3873](https://github.com/hyperf/hyperf/pull/3873) Fixed bug that heartbeat failed when using nacos without default group.
- [#3877](https://github.com/hyperf/hyperf/pull/3877) Fixed bug that heartbeat will be registered more than once.
- [#3879](https://github.com/hyperf/hyperf/pull/3879) Fixed bug that `watcher` does not work caused by proxies replaced.

## Optimized

- [#3877](https://github.com/hyperf/hyperf/pull/3877) Support `lightBeatEnabled` for Nacos heartbeat.

# v2.2.1 - 2021-07-27

## Fixed

- [#3750](https://github.com/hyperf/hyperf/pull/3750) Fixed fatal error which caused by dispatching a non exist namespace when using `socket-io`.
- [#3828](https://github.com/hyperf/hyperf/pull/3828) Fixed bug that lazy inject does not work for `Hyperf\Redis\Redis` in `PHP8.0`.
- [#3845](https://github.com/hyperf/hyperf/pull/3845) Fixed bug that `watcher` does not work for `v2.2`.
- [#3848](https://github.com/hyperf/hyperf/pull/3848) Fixed bug that the usage of registering itself like `nacos v2.1` does not work.
- [#3866](https://github.com/hyperf/hyperf/pull/3866) Fixed bug that the metadata of nacos instance can't be registered successfully.

## Optimized

- [#3763](https://github.com/hyperf/hyperf/pull/3763) Support chained calls for `JsonResource::wrap()` and `JsonResource::withoutWrapping()`.
- [#3843](https://github.com/hyperf/hyperf/pull/3843) Check the status code and body of the response to ensure whether the instance already be registered.
- [#3854](https://github.com/hyperf/hyperf/pull/3854) Support RFC 5987 for `Hyperf\HttpServer\Contract\ResponseInterface::download()` which allows utf-8 encoding, percentage encoded (url-encoded).

# v2.2.0 - 2021-07-19

## Dependencies Upgrade

- Upgraded `friendsofphp/php-cs-fixer` to `^3.0`;
- Upgraded `psr/container` to `^1.0|^2.0`;
- Upgraded `egulias/email-validator` to `^3.0`;
- Upgraded `markrogoyski/math-php` to `^2.0`;
- [3783](https://github.com/hyperf/hyperf/pull/3783) Upgraded `league/flysystem` to `^1.0|^2.0`;

## Dependencies Changed

- [#3577](https://github.com/hyperf/hyperf/pull/3577) `domnikl/statsd` is abandoned and no longer maintained. The author suggests using the `slickdeals/statsd` package instead.

## Changed

- [#3334](https://github.com/hyperf/hyperf/pull/3334) Changed the return value of `LengthAwarePaginator::toArray()` to be consistent with that of `Paginator::toArray()`.
- [#3550](https://github.com/hyperf/hyperf/pull/3550) Removed `broker` and `bootstrap_server` from `kafka`, please use `brokers` and `bootstrap_servers` instead.
- [#3580](https://github.com/hyperf/hyperf/pull/3580) Changed the default priority of aspect to 0.
- [#3582](https://github.com/hyperf/hyperf/pull/3582) Changed the consumer tag of amqp to empty string.
- [#3634](https://github.com/hyperf/hyperf/pull/3634) Use Fork Process strategy to replace BetterReflection strategy.
  - [#3649](https://github.com/hyperf/hyperf/pull/3649) Removed `roave/better-reflection` from `hyperf/database` when using `gen:model`.
  - [#3651](https://github.com/hyperf/hyperf/pull/3651) Removed `roave/better-reflection` from LazyLoader.
  - [#3654](https://github.com/hyperf/hyperf/pull/3654) Removed `roave/better-reflection` from other components.
- [#3676](https://github.com/hyperf/hyperf/pull/3676) Use `promphp/prometheus_client_php` instead of `endclothing/prometheus_client_php`.
- [#3694](https://github.com/hyperf/hyperf/pull/3694) Changed `Hyperf\CircuitBreaker\CircuitBreakerInterface` to support php8.
  - Changed `CircuitBreaker::inc*Counter()` to `CircuitBreaker::incr*Counter()`.
  - Changed type hint for method `AbstractHandler::switch()`.
- [#3706](https://github.com/hyperf/hyperf/pull/3706) Changed the style of writing to `#[Middlewares(FooMiddleware::class)]` from `@Middlewares({@Middleware(FooMiddleware::class)})` in PHP8.
- [#3715](https://github.com/hyperf/hyperf/pull/3715) Restructure nacos component, be sure to reread the documents.
- [#3722](https://github.com/hyperf/hyperf/pull/3722) Removed config `config_apollo.php`, please use `config_center.php` instead.
- [#3725](https://github.com/hyperf/hyperf/pull/3725) Removed config `config_etcd.php`, please use `config_center.php` instead.
- [#3730](https://github.com/hyperf/hyperf/pull/3730) Removed config `brokers` and `update_brokers` from kafka.
- [#3733](https://github.com/hyperf/hyperf/pull/3733) Removed config `zookeeper.php`, please use `config_center.php` instead.
- [#3734](https://github.com/hyperf/hyperf/pull/3734) Split `nacos` into `config-nacos` and `service-governance-nacos`.
  - [#3772](https://github.com/hyperf/hyperf/pull/3772) Fixed bug that nacos driver do not work.
- [#3734](https://github.com/hyperf/hyperf/pull/3734) Renamed `nacos-sdk` as `nacos`.
- [#3737](https://github.com/hyperf/hyperf/pull/3737) Refactor config-center and config driver
  - Added `AbstractDriver` and merge the duplicate code into the abstraction class
  - Added `PipeMessageInterface` to uniform the message struct of config fetcher process
- [#3817](https://github.com/hyperf/hyperf/pull/3817) [#3818](https://github.com/hyperf/hyperf/pull/3818) Split `service-governance-consul` from `service-governance`.
- [#3819](https://github.com/hyperf/hyperf/pull/3819) Use their own configuration below `config_center.php` for config center component which using ETCD and Nacos.

## Deprecated

- [#3636](https://github.com/hyperf/hyperf/pull/3636) `Hyperf\Utils\Resource` will be deprecated in v2.3, please use `Hyperf\Utils\ResourceGenerator` instead.

## Added

- [#3589](https://github.com/hyperf/hyperf/pull/3589) Added DAG component.
- [#3606](https://github.com/hyperf/hyperf/pull/3606) Added RPN component.
- [#3629](https://github.com/hyperf/hyperf/pull/3629) Added `Hyperf\Utils\Channel\ChannelManager` which used to manage channels.
- [#3631](https://github.com/hyperf/hyperf/pull/3631) Support multiplexing for AMQP component.
  - [#3639](https://github.com/hyperf/hyperf/pull/3639) Close push channel and socket when worker exited.
  - [#3640](https://github.com/hyperf/hyperf/pull/3640) Optimized log level for SwooleIO.
  - [#3657](https://github.com/hyperf/hyperf/pull/3657) Fixed memory exhausted for rabbitmq caused by confirm channel.
  - [#3659](https://github.com/hyperf/hyperf/pull/3659) Optimized code which be used to close connection friendly.
  - [#3681](https://github.com/hyperf/hyperf/pull/3681) Fixed bug that rpc client does not work for amqp.
- [#3635](https://github.com/hyperf/hyperf/pull/3635) Added `Hyperf\Utils\CodeGen\PhpParser` which used to generate AST for reflection. 
- [#3648](https://github.com/hyperf/hyperf/pull/3648) Added `Hyperf\Utils\CodeGen\PhpDocReaderManager` to manage `PhpDocReader`.
- [#3679](https://github.com/hyperf/hyperf/pull/3679) Added Nacos SDK component.
  - [#3712](https://github.com/hyperf/hyperf/pull/3712) The input parameters of `InstanceProvider::update()` are modified to make it more friendly.
- [#3698](https://github.com/hyperf/hyperf/pull/3698) Support PHP8 Attribute which can replace doctrine annotations.
- [#3714](https://github.com/hyperf/hyperf/pull/3714) Added ide-helper component.
- [#3722](https://github.com/hyperf/hyperf/pull/3722) Added config-center component.
- [#3728](https://github.com/hyperf/hyperf/pull/3728) Added support for `secret` of Apollo.
- [#3743](https://github.com/hyperf/hyperf/pull/3743) Support custom register for service governance.
- [#3753](https://github.com/hyperf/hyperf/pull/3753) Support long pulling mode for Apollo Client.
- [#3759](https://github.com/hyperf/hyperf/pull/3759) Added `rpc-multiplex` component.
- [#3791](https://github.com/hyperf/hyperf/pull/3791) Support setting multiple annotations by inheriting `AbstractMultipleAnnotation`, such as `@Middleware`.
- [#3806](https://github.com/hyperf/hyperf/pull/3806) Added heartbeat for nacos service governance.

## Optimized

- [#3670](https://github.com/hyperf/hyperf/pull/3670) Adapt database component to support php8.
- [#3673](https://github.com/hyperf/hyperf/pull/3673) Adapt all components to support php8.
- [#3730](https://github.com/hyperf/hyperf/pull/3730) Optimized code for kafka component.
  - Support `timeout` for `Producer` to avoid requests not responding.
  - Removed useless code with pool.
  - Throw exceptions when connect kafka failed.
- [#3758](https://github.com/hyperf/hyperf/pull/3758) Optimized code for pool which get connection again when first failed.

## Fixed

- [#3650](https://github.com/hyperf/hyperf/pull/3650) Fixed bug that `ReflectionParameter::getClass()` will be deprecated in php8.
- [#3692](https://github.com/hyperf/hyperf/pull/3692) Fixed bug that class proxies couldn't be included when building phar.
- [#3769](https://github.com/hyperf/hyperf/pull/3769) Fixed bug that `config-center` conflicts with `metrics`.
- [#3770](https://github.com/hyperf/hyperf/pull/3770) Fixed type error when using `Str::slug()`.
- [#3788](https://github.com/hyperf/hyperf/pull/3788) Fixed type error when using `BladeCompiler::getRawPlaceholder()`.
- [#3794](https://github.com/hyperf/hyperf/pull/3794) Fixed bug that `retry_interval` does not work for `rpc-multiplex`.
- [#3798](https://github.com/hyperf/hyperf/pull/3798) Fixed bug that amqp consumer couldn't restart when rabbitmq server stopped.
- [#3814](https://github.com/hyperf/hyperf/pull/3814) Fixed bug that `libxml_disable_entity_loader()` has been deprecated as of PHP 8.0.0.
