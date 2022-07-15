# Ambient Declaration
- Global: declare const $: JQueryStatic;
- Module:
declare module "foo" {
    export class Bar { ... }
}
- Wildcard Module:
declare module "text!*" {
    const value: string;
    export default value;
}