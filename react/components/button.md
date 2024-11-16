### How add width and margin top (tailwind)

### File 1

    <SubscribeBtn className="mt-3 w-full" />

### File 2

    import { cn } from "@/lib/utils";
    
    export default function SubscribeBtn({ className }) {
      return (
        <button
          className={cn(
            "px-5 py-2 bg-blue-500 rounded text-white font-bold",
            className
          )}
        >
          Subscribe
        </button>
      );
    }
