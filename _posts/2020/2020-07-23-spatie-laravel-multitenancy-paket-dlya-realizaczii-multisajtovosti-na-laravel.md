---
title: "spatie/laravel-multitenancy - пакет для реализации мультисайтовости на laravel"
date: "2020-07-23"
categories: 
  - "php"
tags: 
  - "laravel"
  - "multisites"
---

```
namespace Spatie\Multitenancy\TenantFinder;

use Illuminate\Http\Request;
use Spatie\Multitenancy\Models\Concerns\UsesTenantModel;
use Spatie\Multitenancy\Models\Tenant;

class DomainTenantFinder extends TenantFinder
{
    use UsesTenantModel;

    public function findForRequest(Request $request):?Tenant
    {
        $host = $request->getHost();

        return $this->getTenantModel()::whereDomain($host)->first();
    }
}
```

[https://github.com/spatie/laravel-multitenancy/](https://github.com/spatie/laravel-multitenancy/)
