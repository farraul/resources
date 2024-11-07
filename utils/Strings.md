## Capitalize

    export const capitalize = (keyword: string) => {
      const keywordFormatted = keyword[0].toUpperCase() + keyword.substring(1);
    
      return keywordFormatted;
    };
