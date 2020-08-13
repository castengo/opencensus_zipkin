OpenCensus Zipkin Reporter
=====

[![CircleCI](https://circleci.com/gh/opencensus-beam/opencensus_zipkin.svg?style=svg)](https://circleci.com/gh/opencensus-beam/opencensus_zipkin)
[![Hex.pm](https://img.shields.io/hexpm/v/opencensus_zipkin.svg?style=flat)](https://hex.pm/packages/opencensus_zipkin)

To use, add `opencensus_zipkin` dependency as a runtime application (in rebar3 this means add to the `applications` list of `.app.src`) and set as the reporter in the `opencensus` configuration:

``` erlang
{opencensus, [
    {reporters, [{oc_reporter_zipkin, [{address, "http://localhost:9411/api/v2/spans"},
                                       {signal_fx_token, "SIGNAL_FX_TOKEN"},
                                       {local_endpoint, #{<<"serviceName">> => <<"service">>}]}}]}
    ...]}
```

## Running tests

Need to have rebar3 installed.

`$ rebar3 ct`

