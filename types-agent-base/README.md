# Installation
> `npm install --save @types/agent-base`

# Summary
This package contains type definitions for agent-base (https://github.com/TooTallNate/node-agent-base#readme).

# Details
Files were exported from https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/agent-base.
## [index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/agent-base/index.d.ts)
````ts
// Type definitions for agent-base 4.2
// Project: https://github.com/TooTallNate/node-agent-base#readme
// Definitions by: Christopher Quadflieg <https://github.com/Shinigami92>
// Definitions: https://github.com/DefinitelyTyped/DefinitelyTyped

/// <reference types="node" />
import { EventEmitter } from 'events';

declare namespace Agent {
    type AgentCallback = (
        req?: any,
        opts?: {
            secureEndpoint: boolean;
        }
    ) => void;

    interface AgentOptions {
        timeout?: number | undefined;
        host?: string | undefined;
        port?: number | undefined;
        [key: string]: any;
    }

    interface Agent extends EventEmitter {
        _promisifiedCallback: boolean;
        timeout: number | null;
        options?: AgentOptions | undefined;
        callback: AgentCallback;
        addRequest: (req?: any, opts?: any) => void;
        freeSocket: (socket: any, opts: any) => void;
    }
}

/**
 * Base `http.Agent` implementation.
 * No pooling/keep-alive is implemented by default.
 */
declare function Agent(opts?: Agent.AgentOptions): Agent.Agent;
declare function Agent(
    callback: Agent.AgentCallback,
    opts?: Agent.AgentOptions
): Agent.Agent;

export = Agent;

````

### Additional Details
 * Last updated: Tue, 06 Jul 2021 18:05:31 GMT
 * Dependencies: [@types/node](https://npmjs.com/package/@types/node)
 * Global values: none

# Credits
These definitions were written by [Christopher Quadflieg](https://github.com/Shinigami92).
