### How add width and margin top (tailwind)

### File 1

    import { twMerge } from "tailwind-merge";
    import { clsx, ClassValue } from "clsx";
    
    export function cn(...inputs: ClassValue[]) {
      return twMerge(clsx(inputs));
    }
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

### File 3

    <SubscribeBtn className="mt-3 w-full" />
