# Reference
## vms
<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">list_vms</a>(...) -> ListVmsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.list_vms()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">create_vms</a>(...) -> CreateVmResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new VM and returns it. To preview pricing without creating anything, use `POST /compute/vms/cost-estimate` instead.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi, VmSpecsDto
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.create_vms(
    name="my-new-vm",
    region="us-west-0",
    vm_package="standard-custom",
    vm_specs=VmSpecsDto(
        vcpu=2,
        memory_mb=2048,
        root_disk_gb=50,
    ),
    image="ubuntu-22.04",
    subscription_period="hourly",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateVmDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">get_metrics_vms</a>(...) -> typing.List[VmMetricSampleDto]</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.get_metrics_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
    hours=24,
    sample_period=10,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**hours:** `float` — Number of hours to look back (1-16)
    
</dd>
</dl>

<dl>
<dd>

**sample_period:** `typing.Optional[float]` — Sampling step — return every Nth data point from the raw dataset. Higher values return fewer, more spread-out points. When omitted, up to 150 points are returned.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">reset_password_vms</a>(...) -> VmPasswordResetResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resets the VM password. You can optionally provide a custom password, or let the system generate one. The VM must be stopped for this operation. IMPORTANT: The password is only returned once - save it immediately.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.reset_password_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**password:** `typing.Optional[str]` — Custom password to set for the VM. If not provided, a random password will be generated.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">get_vms</a>(...) -> VmResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.get_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">delete_vms</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.delete_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">get_cost_estimate_vms</a>(...) -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a VM with the given specs without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi, VmSpecsDto
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.get_cost_estimate_vms(
    name="my-new-vm",
    region="us-west-0",
    vm_package="standard-custom",
    vm_specs=VmSpecsDto(
        vcpu=2,
        memory_mb=2048,
        root_disk_gb=50,
    ),
    image="ubuntu-22.04",
    subscription_period="hourly",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateVmDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">power_vms</a>(...) -> VmPowerActionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start, stop, or reboot a virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.power_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
    action="start",
    force=False,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**action:** `PowerVmsRequestAction` — Power action to perform
    
</dd>
</dl>

<dl>
<dd>

**force:** `typing.Optional[bool]` — Whether to force the action (applicable for stop and reboot actions)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">scale_vms</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Scale a virtual machine to new CPU and/or memory specifications. When the VM is stopped, both scale-up and scale-down are allowed. When running, only scale-up is permitted.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.scale_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**cpu:** `typing.Optional[int]` — Number of virtual CPUs. Optional, but at least one of CPU or memory must be provided.
    
</dd>
</dl>

<dl>
<dd>

**memory_mb:** `typing.Optional[int]` — Memory in MB. Optional, but at least one of CPU or memory must be provided.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">resize_disk_vms</a>(...) -> VmDiskResizeResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resizes the root disk of a virtual machine. The new size must be larger than the current root disk size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.resize_disk_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
    size_gb=200,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**size_gb:** `int` — The new size of the root disk in GB. Must be larger than the current root disk size.
    
</dd>
</dl>

<dl>
<dd>

**reboot:** `typing.Optional[bool]` — Whether to automatically reboot the VM after the resize completes. Only applies when the VM is running. A reboot is required for the OS to recognize the new disk size.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">create_console_vms</a>(...) -> VmConsoleResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a console endpoint URL for accessing the VM console. Returns the console URL and optional websocket URL.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.create_console_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">update_hostname_vms</a>(...) -> VmHostnameUpdateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the hostname of a virtual machine. The VM must be stopped and started for the change to take effect.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.update_hostname_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
    hostname="my-web-server",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**hostname:** `str` — The new hostname for the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vms.<a href="src/americancloud/vms/client.py">reinstall_vms</a>(...) -> VmReinstallResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reinstalls a virtual machine from its current template or a new template. This will erase all data on the root disk.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vms.reinstall_vms(
    id="123e4567-e89b-12d3-a456-426614174000",
    image="ubuntu-22.04",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**image:** `typing.Optional[str]` — Optional image label to reinstall from (uses current template if not provided)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## vm-packages
<details><summary><code>client.vm_packages.<a href="src/americancloud/vm_packages/client.py">list_vm_packages</a>(...) -> ListVmPackagesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vm_packages.list_vm_packages()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vm_packages.<a href="src/americancloud/vm_packages/client.py">get_vm_packages</a>(...) -> VmPackageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vm_packages.get_vm_packages(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VM package to get
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vm_packages.<a href="src/americancloud/vm_packages/client.py">get_by_label_vm_packages</a>(...) -> VmPackageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vm_packages.get_by_label_vm_packages(
    label="standard-2-4",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**label:** `str` — Label of the VM package to get
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## regions
<details><summary><code>client.regions.<a href="src/americancloud/regions/client.py">list_regions</a>(...) -> ListRegionsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.regions.list_regions()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.regions.<a href="src/americancloud/regions/client.py">get_regions</a>(...) -> RegionDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.regions.get_regions(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the region to get
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.regions.<a href="src/americancloud/regions/client.py">get_by_label_regions</a>(...) -> RegionDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.regions.get_by_label_regions(
    label="sjc0",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**label:** `str` — Label of the region to get
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## images
<details><summary><code>client.images.<a href="src/americancloud/images/client.py">list_images</a>(...) -> ListImagesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.images.list_images()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**os:** `typing.Optional[str]` — Filter images by operating system
    
</dd>
</dl>

<dl>
<dd>

**version:** `typing.Optional[str]` — Filter images by OS version (used together with os)
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.images.<a href="src/americancloud/images/client.py">get_images</a>(...) -> ImageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.images.get_images(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the image to get
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.images.<a href="src/americancloud/images/client.py">get_by_label_images</a>(...) -> ImageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.images.get_by_label_images(
    label="ubuntu-22.04",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**label:** `str` — Label of the image to get
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## isolated-networks
<details><summary><code>client.isolated_networks.<a href="src/americancloud/isolated_networks/client.py">list_isolated_networks</a>(...) -> ListIsolatedNetworksResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.isolated_networks.list_isolated_networks()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.isolated_networks.<a href="src/americancloud/isolated_networks/client.py">create_isolated_networks</a>(...) -> IsolatedNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.isolated_networks.create_isolated_networks(
    name="production-network",
    region="sjc0",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — Human-readable name for the network.
    
</dd>
</dl>

<dl>
<dd>

**region:** `str` — Region the network will be created in. References a region label from /v1/compute/regions.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Free-form description of the network.
    
</dd>
</dl>

<dl>
<dd>

**netmask:** `typing.Optional[str]` — Network netmask.
    
</dd>
</dl>

<dl>
<dd>

**gateway:** `typing.Optional[str]` — Network gateway IP.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.isolated_networks.<a href="src/americancloud/isolated_networks/client.py">get_isolated_networks</a>(...) -> DetailedIsolatedNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.isolated_networks.get_isolated_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the isolated network
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.isolated_networks.<a href="src/americancloud/isolated_networks/client.py">update_isolated_networks</a>(...) -> IsolatedNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.isolated_networks.update_isolated_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the isolated network to update
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — New name for the network.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — New description for the network.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.isolated_networks.<a href="src/americancloud/isolated_networks/client.py">delete_isolated_networks</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.isolated_networks.delete_isolated_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the isolated network to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.isolated_networks.<a href="src/americancloud/isolated_networks/client.py">restart_isolated_networks</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.isolated_networks.restart_isolated_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the isolated network to restart
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## vpc-networks
<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">list_vpc_networks</a>(...) -> ListVpcNetworksResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.list_vpc_networks()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">create_vpc_networks</a>(...) -> DetailedVpcNetworkResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new VPC. To preview pricing without creating anything, use POST /networks/vpc/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.create_vpc_networks(
    name="production-vpc",
    region="sjc0",
    cidr="10.0.0.0/16",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateVpcNetworkDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">get_vpc_networks</a>(...) -> DetailedVpcNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.get_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC to get
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">update_vpc_networks</a>(...) -> VpcNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.update_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC to update
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — New name for the VPC.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — New description for the VPC.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">delete_vpc_networks</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.delete_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">get_cost_estimate_vpc_networks</a>(...) -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a VPC with the given configuration without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.get_cost_estimate_vpc_networks(
    name="production-vpc",
    region="sjc0",
    cidr="10.0.0.0/16",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateVpcNetworkDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">create_tier_vpc_networks</a>(...) -> VpcTierResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.create_tier_vpc_networks(
    name="web-tier",
    vpc_id="123e4567-e89b-12d3-a456-426614174000",
    gateway="10.0.0.1",
    netmask="255.255.255.0",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — Human-readable name for the network tier.
    
</dd>
</dl>

<dl>
<dd>

**vpc_id:** `str` — Identifier of the parent VPC the tier belongs to.
    
</dd>
</dl>

<dl>
<dd>

**gateway:** `str` — Network gateway IP for the tier.
    
</dd>
</dl>

<dl>
<dd>

**netmask:** `str` — Network netmask for the tier.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Free-form description of the tier.
    
</dd>
</dl>

<dl>
<dd>

**acl_id:** `typing.Optional[str]` — Identifier of the ACL to apply to the tier.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">get_tier_vpc_networks</a>(...) -> VpcTierDetailResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single network tier of a VPC.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.get_tier_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
    tier_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tier_id:** `str` — ID of the network tier
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">update_tier_vpc_networks</a>(...) -> VpcTierDetailResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the name and/or description of a network tier.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.update_tier_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
    tier_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tier_id:** `str` — ID of the network tier to update
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — New name for the tier.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — New description for the tier.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">delete_tier_vpc_networks</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a single network tier from a VPC, leaving the rest of the VPC intact.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.delete_tier_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
    tier_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tier_id:** `str` — ID of the network tier to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">restart_tier_vpc_networks</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Restarts a single network tier of a VPC.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.restart_tier_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
    tier_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tier_id:** `str` — ID of the network tier to restart
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.vpc_networks.<a href="src/americancloud/vpc_networks/client.py">restart_vpc_networks</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.vpc_networks.restart_vpc_networks(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the VPC to restart
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## public-ips
<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">list_public_ips</a>(...) -> ListPublicIpsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.list_public_ips()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">reserve_public_ips</a>(...) -> PublicIpResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reserves a public IP address and associates it with the specified virtual machine. The region is automatically inferred from the virtual machine. To preview pricing without reserving anything, use POST /networks/public-ip/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.reserve_public_ips(
    region="us-west-0",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**region:** `str` — Label of the region where the IP address should be allocated
    
</dd>
</dl>

<dl>
<dd>

**network_id:** `typing.Optional[str]` — Identifier of the isolated network the public IP should attach to.
    
</dd>
</dl>

<dl>
<dd>

**vpc_id:** `typing.Optional[str]` — Identifier of the VPC the public IP should attach to.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">list_by_isolated_network_public_ips</a>(...) -> ListByIsolatedNetworkPublicIpsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.list_by_isolated_network_public_ips(
    isolated_network_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**isolated_network_id:** `str` — ID of the isolated network
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">list_by_vpc_public_ips</a>(...) -> ListByVpcPublicIpsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.list_by_vpc_public_ips(
    vpc_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**vpc_id:** `str` — ID of the VPC
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">get_public_ips</a>(...) -> PublicIpResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.get_public_ips(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">release_public_ips</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.release_public_ips(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the public IP address to release
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">get_cost_estimate_public_ips</a>() -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost of reserving a public IP address without reserving one.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.get_cost_estimate_public_ips()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">change_source_nat_ip_public_ips</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Changes the source NAT IP for the specified public IP address
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.change_source_nat_ip_public_ips(
    id="123e4567-e89b-12d3-a456-426614174000",
    network_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the public IP address to change
    
</dd>
</dl>

<dl>
<dd>

**network_id:** `str` — Identifier of the network whose source NAT IP should be replaced.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">enable_static_nat_public_ips</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Enables static NAT for the specified public IP by associating it with a virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.enable_static_nat_public_ips(
    id="123e4567-e89b-12d3-a456-426614174000",
    virtual_machine_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**virtual_machine_id:** `str` — Identifier of the virtual machine to associate with this public IP.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_ips.<a href="src/americancloud/public_ips/client.py">disable_static_nat_public_ips</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Disables static NAT for the specified public IP address
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.public_ips.disable_static_nat_public_ips(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## firewall-rules
<details><summary><code>client.firewall_rules.<a href="src/americancloud/firewall_rules/client.py">list_firewall_rules</a>(...) -> ListFirewallRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.firewall_rules.list_firewall_rules(
    ip_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ip_id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.firewall_rules.<a href="src/americancloud/firewall_rules/client.py">create_firewall_rules</a>(...) -> FirewallRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.firewall_rules.create_firewall_rules(
    ip_id="123e4567-e89b-12d3-a456-426614174000",
    protocol="TCP",
    source_cidr_list="10.0.0.0/24",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ip_id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `CreateFirewallRuleDtoProtocol` — Protocol the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**source_cidr_list:** `str` — Source CIDR allowed to reach the rule target.
    
</dd>
</dl>

<dl>
<dd>

**start_port:** `typing.Optional[int]` — Start of the port range (1-65535). Required for TCP and UDP.
    
</dd>
</dl>

<dl>
<dd>

**end_port:** `typing.Optional[int]` — End of the port range (1-65535). Must be greater than or equal to `startPort`.
    
</dd>
</dl>

<dl>
<dd>

**type:** `typing.Optional[CreateFirewallRuleDtoType]` — Direction of traffic this rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.firewall_rules.<a href="src/americancloud/firewall_rules/client.py">delete_firewall_rules</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.firewall_rules.delete_firewall_rules(
    rule_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**rule_id:** `str` — ID of the firewall rule to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## port-forwarding
<details><summary><code>client.port_forwarding.<a href="src/americancloud/port_forwarding/client.py">list_port_forwarding</a>(...) -> ListPortForwardingResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.port_forwarding.list_port_forwarding(
    ip_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ip_id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.port_forwarding.<a href="src/americancloud/port_forwarding/client.py">create_port_forwarding</a>(...) -> PortForwardingRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.port_forwarding.create_port_forwarding(
    ip_id="123e4567-e89b-12d3-a456-426614174000",
    private_port="80",
    public_port="8080",
    protocol="TCP",
    vm_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ip_id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**private_port:** `str` — Port on the VM that traffic is forwarded to. Must be 1-65535.
    
</dd>
</dl>

<dl>
<dd>

**public_port:** `str` — Port on the public IP that receives the inbound traffic. Must be 1-65535.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `CreatePortForwardingRuleDtoProtocol` — Protocol the forwarding rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**vm_id:** `str` — Identifier of the VM the forwarded traffic is delivered to.
    
</dd>
</dl>

<dl>
<dd>

**open_firewall:** `typing.Optional[str]` — When `true`, automatically creates a matching firewall rule alongside the port forwarding rule.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.port_forwarding.<a href="src/americancloud/port_forwarding/client.py">delete_port_forwarding</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.port_forwarding.delete_port_forwarding(
    rule_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**rule_id:** `str` — ID of the port forwarding rule to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## load-balancer-rules
<details><summary><code>client.load_balancer_rules.<a href="src/americancloud/load_balancer_rules/client.py">list_load_balancer_rules</a>(...) -> ListLoadBalancerRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.load_balancer_rules.list_load_balancer_rules(
    ip_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ip_id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.load_balancer_rules.<a href="src/americancloud/load_balancer_rules/client.py">create_load_balancer_rules</a>(...) -> LoadBalancerRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.load_balancer_rules.create_load_balancer_rules(
    ip_id="123e4567-e89b-12d3-a456-426614174000",
    name="web-lb",
    algorithm="roundrobin",
    public_port="80",
    private_port="8080",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ip_id:** `str` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Name of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**algorithm:** `CreateLoadBalancerRuleDtoAlgorithm` — Algorithm used to distribute traffic across the backend VMs.
    
</dd>
</dl>

<dl>
<dd>

**public_port:** `str` — Public port the load balancer listens on.
    
</dd>
</dl>

<dl>
<dd>

**private_port:** `str` — Port on the backend VMs that traffic is forwarded to.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `typing.Optional[CreateLoadBalancerRuleDtoProtocol]` — Protocol the load balancer accepts.
    
</dd>
</dl>

<dl>
<dd>

**source_cidr_list:** `typing.Optional[str]` — Source CIDR allowed to reach the load balancer.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Free-form description of the rule.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.load_balancer_rules.<a href="src/americancloud/load_balancer_rules/client.py">update_load_balancer_rules</a>(...) -> LoadBalancerRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.load_balancer_rules.update_load_balancer_rules(
    rule_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**rule_id:** `str` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — New name for the rule.
    
</dd>
</dl>

<dl>
<dd>

**algorithm:** `typing.Optional[UpdateLoadBalancerRuleDtoAlgorithm]` — New algorithm used to distribute traffic.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — New description for the rule.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `typing.Optional[str]` — New protocol the load balancer accepts.
    
</dd>
</dl>

<dl>
<dd>

**source_cidr_list:** `typing.Optional[str]` — New source CIDR allowed to reach the load balancer.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.load_balancer_rules.<a href="src/americancloud/load_balancer_rules/client.py">delete_load_balancer_rules</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.load_balancer_rules.delete_load_balancer_rules(
    rule_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**rule_id:** `str` — ID of the load balancer rule to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.load_balancer_rules.<a href="src/americancloud/load_balancer_rules/client.py">list_instances_load_balancer_rules</a>(...) -> ListInstancesLoadBalancerRulesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns assigned VMs by default. Set applied=false to list VMs available for assignment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.load_balancer_rules.list_instances_load_balancer_rules(
    rule_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**rule_id:** `str` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**applied:** `typing.Optional[bool]` — If true (default), returns assigned VMs. If false, returns VMs available for assignment.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.load_balancer_rules.<a href="src/americancloud/load_balancer_rules/client.py">assign_vms_load_balancer_rules</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.load_balancer_rules.assign_vms_load_balancer_rules(
    rule_id="123e4567-e89b-12d3-a456-426614174000",
    vm_ids=[
        "123e4567-e89b-12d3-a456-426614174000"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**rule_id:** `str` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**request:** `AssignVmsToLoadBalancerRuleDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.load_balancer_rules.<a href="src/americancloud/load_balancer_rules/client.py">remove_vms_load_balancer_rules</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.load_balancer_rules.remove_vms_load_balancer_rules(
    rule_id="123e4567-e89b-12d3-a456-426614174000",
    vm_ids=[
        "123e4567-e89b-12d3-a456-426614174000"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**rule_id:** `str` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**request:** `AssignVmsToLoadBalancerRuleDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## egress-rules
<details><summary><code>client.egress_rules.<a href="src/americancloud/egress_rules/client.py">list_egress_rules</a>(...) -> ListEgressRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.egress_rules.list_egress_rules()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.egress_rules.<a href="src/americancloud/egress_rules/client.py">create_egress_rules</a>(...) -> EgressRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.egress_rules.create_egress_rules(
    protocol="TCP",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**protocol:** `str` — Protocol the rule applies to. One of `TCP`, `UDP`, `ICMP`, or `ALL`.
    
</dd>
</dl>

<dl>
<dd>

**start_port:** `typing.Optional[int]` — Start of the port range the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**end_port:** `typing.Optional[int]` — End of the port range the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**source_cidr_list:** `typing.Optional[str]` — Source CIDR within the guest network CIDR. Omit to allow the entire network.
    
</dd>
</dl>

<dl>
<dd>

**dest_cidr_list:** `typing.Optional[str]` — Destination CIDR the traffic is allowed to reach. Defaults to `0.0.0.0/0`.
    
</dd>
</dl>

<dl>
<dd>

**network_id:** `typing.Optional[str]` — Identifier of the network the egress rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.egress_rules.<a href="src/americancloud/egress_rules/client.py">list_by_network_egress_rules</a>(...) -> ListByNetworkEgressRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.egress_rules.list_by_network_egress_rules(
    network_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**network_id:** `str` — ID of the network
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.egress_rules.<a href="src/americancloud/egress_rules/client.py">get_egress_rules</a>(...) -> EgressRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.egress_rules.get_egress_rules(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the egress rule
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.egress_rules.<a href="src/americancloud/egress_rules/client.py">update_egress_rules</a>(...) -> EgressRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.egress_rules.update_egress_rules(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the egress rule
    
</dd>
</dl>

<dl>
<dd>

**source_cidr_list:** `typing.Optional[str]` — Source CIDR within the guest network CIDR.
    
</dd>
</dl>

<dl>
<dd>

**dest_cidr_list:** `typing.Optional[str]` — Destination CIDR the traffic is allowed to reach.
    
</dd>
</dl>

<dl>
<dd>

**start_port:** `typing.Optional[int]` — Start of the port range the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**end_port:** `typing.Optional[int]` — End of the port range the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.egress_rules.<a href="src/americancloud/egress_rules/client.py">delete_egress_rules</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.egress_rules.delete_egress_rules(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the egress rule to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## network-acls
<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">list_lists_network_acls</a>(...) -> ListListsNetworkAclsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.list_lists_network_acls()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">create_list_network_acls</a>(...) -> NetworkAclListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.create_list_network_acls(
    name="web-tier-acl",
    vpc_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — Human-readable name for the ACL list.
    
</dd>
</dl>

<dl>
<dd>

**vpc_id:** `str` — Identifier of the parent VPC the ACL list belongs to.
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Free-form description of the ACL list.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">list_lists_by_vpc_network_acls</a>(...) -> ListListsByVpcNetworkAclsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.list_lists_by_vpc_network_acls(
    vpc_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**vpc_id:** `str` — ID of the VPC
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">get_list_network_acls</a>(...) -> NetworkAclListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.get_list_network_acls(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Network ACL List
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">delete_list_network_acls</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.delete_list_network_acls(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Network ACL List to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">list_rules_network_acls</a>(...) -> ListRulesNetworkAclsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.list_rules_network_acls(
    list_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**list_id:** `str` — ID of the Network ACL List
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">create_rule_network_acls</a>(...) -> NetworkAclRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.create_rule_network_acls(
    list_id="123e4567-e89b-12d3-a456-426614174000",
    cidr_list="0.0.0.0/0",
    protocol="TCP",
    action="Allow",
    traffic_type="Ingress",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**list_id:** `str` — ID of the Network ACL List
    
</dd>
</dl>

<dl>
<dd>

**cidr_list:** `str` — Remote CIDR — source CIDR for `Ingress` rules, destination CIDR for `Egress` rules.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `str` — Protocol the rule applies to. One of `TCP`, `UDP`, `ICMP`, or `ALL`.
    
</dd>
</dl>

<dl>
<dd>

**action:** `str` — Whether to allow or deny matching traffic.
    
</dd>
</dl>

<dl>
<dd>

**traffic_type:** `str` — Direction of traffic the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**number:** `typing.Optional[str]` — Rule number (1-1000). Unique within the ACL list and determines evaluation order.
    
</dd>
</dl>

<dl>
<dd>

**start_port:** `typing.Optional[int]` — Start of the port range. Used for `TCP` and `UDP` protocols.
    
</dd>
</dl>

<dl>
<dd>

**end_port:** `typing.Optional[int]` — End of the port range. Used for `TCP` and `UDP` protocols.
    
</dd>
</dl>

<dl>
<dd>

**icmp_type:** `typing.Optional[str]` — ICMP message type. Used for the `ICMP` protocol.
    
</dd>
</dl>

<dl>
<dd>

**icmp_code:** `typing.Optional[str]` — ICMP message code. Used for the `ICMP` protocol.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">get_rule_network_acls</a>(...) -> NetworkAclRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.get_rule_network_acls(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Network ACL Rule
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">delete_rule_network_acls</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.delete_rule_network_acls(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Network ACL Rule to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.network_acls.<a href="src/americancloud/network_acls/client.py">replace_list_network_acls</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Replaces the ACL List for a network with the specified ACL List
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.network_acls.replace_list_network_acls(
    id="123e4567-e89b-12d3-a456-426614174000",
    network_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Network ACL List to apply
    
</dd>
</dl>

<dl>
<dd>

**network_id:** `str` — Identifier of the network the ACL list should be applied to.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## databases
<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">list_databases</a>(...) -> ListDatabasesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all database clusters for the authenticated account.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.list_databases()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_cluster_id:** `typing.Optional[str]` — Filter by infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">create_databases</a>(...) -> CreateClusterResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new managed database cluster for the authenticated account.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.create_databases(
    db_cluster_name="production-db",
    region_id="123e4567-e89b-12d3-a456-426614174000",
    tier="standard",
    availability_type="single-node",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**db_cluster_name:** `str` — Database cluster name. Must comply with Kubernetes naming rules.
    
</dd>
</dl>

<dl>
<dd>

**region_id:** `str` — Identifier of the region the cluster will run in.
    
</dd>
</dl>

<dl>
<dd>

**tier:** `str` — Infrastructure tier that determines per-node CPU and memory.
    
</dd>
</dl>

<dl>
<dd>

**availability_type:** `CreateDatabaseClusterDtoAvailabilityType` — Availability mode for the cluster.
    
</dd>
</dl>

<dl>
<dd>

**user_cluster_id:** `typing.Optional[str]` — Identifier of an existing infrastructure cluster to deploy the database on. Omit to provision new infrastructure.
    
</dd>
</dl>

<dl>
<dd>

**ssh_key:** `typing.Optional[str]` — SSH key authorized for access to the cluster. Required when creating a new cluster; omit only when deploying onto an existing `userClusterId`.
    
</dd>
</dl>

<dl>
<dd>

**offering_id:** `typing.Optional[str]` — Identifier of the database offering to use.
    
</dd>
</dl>

<dl>
<dd>

**offering_name:** `typing.Optional[str]` — Name of the database offering. Alternative to `offeringId` for selecting an offering.
    
</dd>
</dl>

<dl>
<dd>

**storage_gb:** `typing.Optional[int]` — Storage capacity allocated to the cluster, in gigabytes.
    
</dd>
</dl>

<dl>
<dd>

**network_config:** `typing.Optional[CreateDatabaseClusterDtoNetworkConfig]` — Network the cluster will attach to. Required when creating a new cluster; omit only when deploying onto an existing `userClusterId`.
    
</dd>
</dl>

<dl>
<dd>

**restore:** `typing.Optional[CreateClusterRestoreDto]` — Restore-from-backup configuration. Provide to bootstrap the new cluster from an existing backup.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">get_cost_estimate_databases</a>(...) -> DbsCostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated monthly cost for deploying a database. If user_cluster_id is provided, calculates the marginal cost on an existing cluster.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.get_cost_estimate_databases(
    offering_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**offering_id:** `str` — Database offering ID
    
</dd>
</dl>

<dl>
<dd>

**user_cluster_id:** `typing.Optional[str]` — Existing infrastructure cluster ID for marginal cost calculation
    
</dd>
</dl>

<dl>
<dd>

**availability_type:** `typing.Optional[str]` — Availability type: "single-node" or "data-redundancy"
    
</dd>
</dl>

<dl>
<dd>

**storage_gb:** `typing.Optional[str]` — Custom storage size in GB
    
</dd>
</dl>

<dl>
<dd>

**tier:** `typing.Optional[str]` — Infrastructure tier: "standard" or "premium"
    
</dd>
</dl>

<dl>
<dd>

**db_cluster_id:** `typing.Optional[str]` — Database cluster ID for resize cost estimates (replaces workload instead of adding)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">get_databases</a>(...) -> ClusterDetailResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.get_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">delete_databases</a>(...) -> ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a database cluster. This operation cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.delete_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">get_status_databases</a>(...) -> ClusterStatusResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.get_status_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">get_connection_databases</a>(...) -> ConnectionInfoResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns connection details for the database cluster.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.get_connection_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    include_password="includePassword",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**include_password:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">get_operations_databases</a>(...) -> RecentOperationsResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.get_operations_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">start_databases</a>(...) -> ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.start_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">stop_databases</a>(...) -> ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.stop_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">resize_databases</a>(...) -> ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Changes the database cluster to a different offering or storage size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.resize_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    offering_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**offering_id:** `str` — Identifier of the target database offering to resize to.
    
</dd>
</dl>

<dl>
<dd>

**storage_gb:** `typing.Optional[int]` — New storage capacity for the cluster, in gigabytes.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">modify_load_balancer_databases</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.modify_load_balancer_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    type="public",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**type:** `ModifyLoadBalancerDatabasesRequestType` — Load balancer type
    
</dd>
</dl>

<dl>
<dd>

**cidr:** `typing.Optional[str]` — CIDR range allowed to reach the load balancer.
    
</dd>
</dl>

<dl>
<dd>

**load_balancer_ip:** `typing.Optional[str]` — Pre-allocated private IP address for the load balancer.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.databases.<a href="src/americancloud/databases/client.py">delete_load_balancer_databases</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.databases.delete_load_balancer_databases(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    type="public",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**type:** `DeleteLoadBalancerDatabasesRequestType` — Load balancer type
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-backups
<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">set_active_repo_database_backups</a>(...) -> BackupRepoUpdateResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.set_active_repo_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    repo_name="primary-backup-repo",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repo_name:** `str` — Name of the backup repository to set as active.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">list_database_backups</a>(...) -> BackupListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.list_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">trigger_database_backups</a>(...) -> BackupTriggerResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.trigger_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    backup_method="xtrabackup",
    backup_policy_name="default-backup-policy",
    backup_name="manual-2026-05-29",
    retention_period="30d",
    deletion_policy="Delete",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**backup_method:** `TriggerBackupRequestDtoBackupMethod` — Backup method to use for this run.
    
</dd>
</dl>

<dl>
<dd>

**backup_policy_name:** `str` — Backup policy that governs this run.
    
</dd>
</dl>

<dl>
<dd>

**backup_name:** `str` — Name to assign to the resulting backup artifact.
    
</dd>
</dl>

<dl>
<dd>

**retention_period:** `str` — How long to keep the backup. Number followed by `d` (days), `h` (hours), or `m` (minutes).
    
</dd>
</dl>

<dl>
<dd>

**deletion_policy:** `TriggerBackupRequestDtoDeletionPolicy` — Action to take on the backup artifact when the policy is removed.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">get_config_database_backups</a>(...) -> BackupClusterConfigResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.get_config_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">get_schedule_database_backups</a>(...) -> BackupScheduleListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.get_schedule_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**schedule_name:** `typing.Optional[str]` — Filter by schedule name
    
</dd>
</dl>

<dl>
<dd>

**backup_policy_name:** `typing.Optional[str]` — Filter by backup policy name
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">create_schedule_database_backups</a>(...) -> BackupRepoSetupResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi, BackupScheduleItemDto
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.create_schedule_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    schedule_name="production-backups",
    backup_policy_name="default-backup-policy",
    schedules=[
        BackupScheduleItemDto(
            name="nightly-full",
            backup_method="xtrabackup",
            cron_expression="0 3 * * *",
        )
    ],
    pitr_enabled=False,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `ModifyBackupScheduleRequestDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">update_schedule_database_backups</a>(...) -> BackupRepoUpdateResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi, BackupScheduleItemDto
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.update_schedule_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    schedule_name="production-backups",
    backup_policy_name="default-backup-policy",
    schedules=[
        BackupScheduleItemDto(
            name="nightly-full",
            backup_method="xtrabackup",
            cron_expression="0 3 * * *",
        )
    ],
    pitr_enabled=False,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `ModifyBackupScheduleRequestDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">delete_schedule_database_backups</a>(...) -> BackupRepoDeleteResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.delete_schedule_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    schedule_name="schedule_name",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**schedule_name:** `str` — Name of the backup schedule to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">get_policy_database_backups</a>(...) -> BackupPolicyListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.get_policy_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**policy_name:** `typing.Optional[str]` — Filter by policy name
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">get_database_backups</a>(...) -> BackupDetailsResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.get_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    backup_name="nightly-2026-05-28",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**backup_name:** `str` — Backup name
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_backups.<a href="src/americancloud/database_backups/client.py">delete_database_backups</a>(...) -> BackupDeleteResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_backups.delete_database_backups(
    cluster_id="123e4567-e89b-12d3-a456-426614174000",
    backup_name="nightly-2026-05-28",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cluster_id:** `str` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**backup_name:** `str` — Backup name
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-offerings
<details><summary><code>client.database_offerings.<a href="src/americancloud/database_offerings/client.py">list_database_offerings</a>(...) -> ListDatabaseOfferingsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all active database offerings. Optionally filter by database type.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_offerings.list_database_offerings()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**type:** `typing.Optional[ListDatabaseOfferingsRequestType]` — Filter by database type
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_offerings.<a href="src/americancloud/database_offerings/client.py">get_database_offerings</a>(...) -> DatabaseOfferingResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_offerings.get_database_offerings(
    offering_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**offering_id:** `str` — Database offering ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-regions
<details><summary><code>client.database_regions.<a href="src/americancloud/database_regions/client.py">list_database_regions</a>() -> DbaasRegionsResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all regions with their available infrastructure tiers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_regions.list_database_regions()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-infrastructure
<details><summary><code>client.database_infrastructure.<a href="src/americancloud/database_infrastructure/client.py">list_database_infrastructure</a>(...) -> ListDatabaseInfrastructureResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all infrastructure clusters for the authenticated account with their associated database clusters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_infrastructure.list_database_infrastructure()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_infrastructure.<a href="src/americancloud/database_infrastructure/client.py">get_database_infrastructure</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_infrastructure.get_database_infrastructure(
    user_cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_cluster_id:** `str` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_infrastructure.<a href="src/americancloud/database_infrastructure/client.py">list_backup_repos_database_infrastructure</a>(...) -> BackupRepoListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_infrastructure.list_backup_repos_database_infrastructure(
    user_cluster_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_cluster_id:** `str` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_infrastructure.<a href="src/americancloud/database_infrastructure/client.py">create_backup_repo_database_infrastructure</a>(...) -> BackupRepoSetupResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_infrastructure.create_backup_repo_database_infrastructure(
    user_cluster_id="123e4567-e89b-12d3-a456-426614174000",
    repo_name="primary-backup-repo",
    bucket="my-storage-bucket",
    endpoint="https://s3.example.com",
    access_key_id="AKIAIOSFODNN7EXAMPLE",
    access_key_secret="wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_cluster_id:** `str` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repo_name:** `str` — Name for the backup repository.
    
</dd>
</dl>

<dl>
<dd>

**bucket:** `str` — S3 bucket backups are stored in.
    
</dd>
</dl>

<dl>
<dd>

**endpoint:** `str` — S3-compatible endpoint URL to use for the bucket.
    
</dd>
</dl>

<dl>
<dd>

**access_key_id:** `str` — S3 access key identifier with access to the bucket.
    
</dd>
</dl>

<dl>
<dd>

**access_key_secret:** `str` — S3 secret key paired with the access key.
    
</dd>
</dl>

<dl>
<dd>

**path_prefix:** `typing.Optional[str]` — Optional key prefix to store backups under, inside the bucket.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_infrastructure.<a href="src/americancloud/database_infrastructure/client.py">update_backup_repo_database_infrastructure</a>(...) -> BackupRepoUpdateResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_infrastructure.update_backup_repo_database_infrastructure(
    user_cluster_id="123e4567-e89b-12d3-a456-426614174000",
    repo_name="primary-backup-repo",
    bucket="my-storage-bucket",
    endpoint="https://s3.example.com",
    access_key_id="AKIAIOSFODNN7EXAMPLE",
    access_key_secret="wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_cluster_id:** `str` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repo_name:** `str` — Name for the backup repository.
    
</dd>
</dl>

<dl>
<dd>

**bucket:** `str` — S3 bucket backups are stored in.
    
</dd>
</dl>

<dl>
<dd>

**endpoint:** `str` — S3-compatible endpoint URL to use for the bucket.
    
</dd>
</dl>

<dl>
<dd>

**access_key_id:** `str` — S3 access key identifier with access to the bucket.
    
</dd>
</dl>

<dl>
<dd>

**access_key_secret:** `str` — S3 secret key paired with the access key.
    
</dd>
</dl>

<dl>
<dd>

**path_prefix:** `typing.Optional[str]` — Optional key prefix to store backups under, inside the bucket.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_infrastructure.<a href="src/americancloud/database_infrastructure/client.py">get_backup_repo_database_infrastructure</a>(...) -> BackupRepoStatusResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_infrastructure.get_backup_repo_database_infrastructure(
    user_cluster_id="123e4567-e89b-12d3-a456-426614174000",
    repo_name="primary-backup-repo",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_cluster_id:** `str` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repo_name:** `str` — Backup repository name
    
</dd>
</dl>

<dl>
<dd>

**include_credentials:** `typing.Optional[str]` — Include repository credentials in response (default: false)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database_infrastructure.<a href="src/americancloud/database_infrastructure/client.py">delete_backup_repo_database_infrastructure</a>(...) -> BackupRepoDeleteResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_infrastructure.delete_backup_repo_database_infrastructure(
    user_cluster_id="123e4567-e89b-12d3-a456-426614174000",
    repo_name="primary-backup-repo",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_cluster_id:** `str` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repo_name:** `str` — Backup repository name
    
</dd>
</dl>

<dl>
<dd>

**mode:** `typing.Optional[DeleteBackupRepoDatabaseInfrastructureRequestMode]` — Deletion mode: retire (default) or destroy
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-operations
<details><summary><code>client.database_operations.<a href="src/americancloud/database_operations/client.py">get_status_database_operations</a>(...) -> OperationStatusResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed status for a database operation including progress of child commands.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.database_operations.get_status_database_operations(
    correlation_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**correlation_id:** `str` — Operation correlation ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## dns-zones
<details><summary><code>client.dns_zones.<a href="src/americancloud/dns_zones/client.py">list_dns_zones</a>(...) -> ListDnsZonesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.dns_zones.list_dns_zones()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.dns_zones.<a href="src/americancloud/dns_zones/client.py">create_dns_zones</a>(...) -> ZoneResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.dns_zones.create_dns_zones(
    name="example.com",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — The domain name for the DNS zone (e.g. example.com)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.dns_zones.<a href="src/americancloud/dns_zones/client.py">delete_dns_zones</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.dns_zones.delete_dns_zones(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the DNS zone to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## dns-records
<details><summary><code>client.dns_records.<a href="src/americancloud/dns_records/client.py">list_dns_records</a>(...) -> ListDnsRecordsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.dns_records.list_dns_records(
    zone_id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zone_id:** `str` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.dns_records.<a href="src/americancloud/dns_records/client.py">create_dns_records</a>(...) -> RecordResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.dns_records.create_dns_records(
    zone_id="123e4567-e89b-12d3-a456-426614174000",
    name="www",
    type="A",
    content="93.184.216.34",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zone_id:** `str` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Hostname for the record. Use @ for the zone apex.
    
</dd>
</dl>

<dl>
<dd>

**type:** `CreateRecordDtoType` — Record type
    
</dd>
</dl>

<dl>
<dd>

**content:** `str` — Record value (IP address, hostname, text, etc.)
    
</dd>
</dl>

<dl>
<dd>

**ttl:** `typing.Optional[float]` — Time to live in seconds (60–86400)
    
</dd>
</dl>

<dl>
<dd>

**priority:** `typing.Optional[int]` — Priority (required for MX and SRV records)
    
</dd>
</dl>

<dl>
<dd>

**weight:** `typing.Optional[int]` — Weight (required for SRV records)
    
</dd>
</dl>

<dl>
<dd>

**port:** `typing.Optional[int]` — Port (required for SRV records)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.dns_records.<a href="src/americancloud/dns_records/client.py">update_dns_records</a>(...) -> RecordResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.dns_records.update_dns_records(
    zone_id="123e4567-e89b-12d3-a456-426614174000",
    current_name="www",
    current_type="A",
    name="www",
    type="A",
    content="93.184.216.34",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zone_id:** `str` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**current_name:** `str` — Current record hostname identifying the record to update (use @ for apex)
    
</dd>
</dl>

<dl>
<dd>

**current_type:** `str` — Current record type identifying the record to update (A, AAAA, CNAME, MX, NS, SRV, TXT)
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Hostname for the record. Use @ for the zone apex.
    
</dd>
</dl>

<dl>
<dd>

**type:** `UpdateRecordDtoType` — Record type
    
</dd>
</dl>

<dl>
<dd>

**content:** `str` — Record value (IP address, hostname, text, etc.)
    
</dd>
</dl>

<dl>
<dd>

**ttl:** `typing.Optional[float]` — Time to live in seconds (60–86400)
    
</dd>
</dl>

<dl>
<dd>

**priority:** `typing.Optional[int]` — Priority (required for MX and SRV records)
    
</dd>
</dl>

<dl>
<dd>

**weight:** `typing.Optional[int]` — Weight (required for SRV records)
    
</dd>
</dl>

<dl>
<dd>

**port:** `typing.Optional[int]` — Port (required for SRV records)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.dns_records.<a href="src/americancloud/dns_records/client.py">delete_dns_records</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.dns_records.delete_dns_records(
    zone_id="123e4567-e89b-12d3-a456-426614174000",
    name="www",
    type="A",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zone_id:** `str` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Record hostname (use @ for apex)
    
</dd>
</dl>

<dl>
<dd>

**type:** `str` — Record type
    
</dd>
</dl>

<dl>
<dd>

**content:** `typing.Optional[str]` — Specific record value to remove. Used for multi-value MX/NS/TXT record sets to target a single entry.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## kubernetes
<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">list_versions_kubernetes</a>(...) -> ListVersionsKubernetesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all available versions. If current_version is provided, returns only versions that are valid upgrade targets (higher version, max one minor version jump).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.list_versions_kubernetes(
    current_version="1.28.4",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**current_version:** `typing.Optional[str]` — Current cluster version to filter upgradeable versions from
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">list_packages_kubernetes</a>(...) -> ListPackagesKubernetesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.list_packages_kubernetes()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">list_clusters_kubernetes</a>(...) -> ListClustersKubernetesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.list_clusters_kubernetes()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">get_cluster_kubernetes</a>(...) -> KubernetesClusterResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns cluster details. Set details=true to include node instances and attached storage volumes.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.get_cluster_kubernetes(
    id="123e4567-e89b-12d3-a456-426614174000",
    details=False,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**details:** `typing.Optional[bool]` — Include node instances and storage volumes in the response
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">delete_cluster_kubernetes</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.delete_cluster_kubernetes(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">create_cluster_kubernetes</a>(...) -> KubernetesClusterResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new Kubernetes cluster for the authenticated account. To preview pricing without creating anything, use POST /kubernetes/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.create_cluster_kubernetes(
    name="my-cluster",
    package="my-package",
    region="us-west-0",
    version="1.28.4",
    control_nodes=1,
    worker_nodes=3,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateKubernetesClusterRequest` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">get_cost_estimate_kubernetes</a>(...) -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a cluster with the given configuration without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.get_cost_estimate_kubernetes(
    name="my-cluster",
    package="my-package",
    region="us-west-0",
    version="1.28.4",
    control_nodes=1,
    worker_nodes=3,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateKubernetesClusterRequest` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">cluster_power_kubernetes</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start or stop a Kubernetes cluster
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.cluster_power_kubernetes(
    id="123e4567-e89b-12d3-a456-426614174000",
    action="start",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**action:** `ClusterPowerKubernetesRequestAction` — Power action to perform
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">get_cluster_config_kubernetes</a>(...) -> KubernetesConfigResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the kubeconfig file content for connecting to the cluster
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.get_cluster_config_kubernetes(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">scale_cluster_kubernetes</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Scale worker nodes, or enable/disable autoscaling with min/max bounds. At least one parameter must be provided.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.scale_cluster_kubernetes(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**worker_nodes:** `typing.Optional[float]` — Number of worker nodes
    
</dd>
</dl>

<dl>
<dd>

**autoscaling_enabled:** `typing.Optional[bool]` — Enable or disable autoscaling
    
</dd>
</dl>

<dl>
<dd>

**min_workers:** `typing.Optional[float]` — Minimum number of worker nodes when autoscaling is enabled
    
</dd>
</dl>

<dl>
<dd>

**max_workers:** `typing.Optional[float]` — Maximum number of worker nodes when autoscaling is enabled
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.kubernetes.<a href="src/americancloud/kubernetes/client.py">upgrade_cluster_kubernetes</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upgrade to a newer Kubernetes version. Use GET /versions to list available versions.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.kubernetes.upgrade_cluster_kubernetes(
    id="123e4567-e89b-12d3-a456-426614174000",
    version="1.29.0",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**version:** `str` — Kubernetes version to upgrade to (semantic version)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## object-storage
<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">list_units_object_storage</a>(...) -> ListUnitsObjectStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all non-deleted object storage units (UIDs) for the authenticated account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.list_units_object_storage(
    usage=False,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**usage:** `typing.Optional[bool]` — Include latest usage report for each storage unit
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">create_unit_object_storage</a>(...) -> ObjectStorageUnitDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new object storage unit for the authenticated account and returns it. The returned storageUnitId identifies the unit in all other object storage requests. To preview pricing without creating anything, use POST /object-storage/units/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.create_unit_object_storage(
    name="storageunit01",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — Storage unit name. Alphanumeric characters only.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">list_buckets_object_storage</a>(...) -> ListBucketsObjectStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all buckets and their statistics for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.list_buckets_object_storage(
    storage_unit_id="tenant$user",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storage_unit_id:** `str` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">create_bucket_object_storage</a>(...) -> ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new bucket for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.create_bucket_object_storage(
    storage_unit_id="tenant$user",
    name="my-storage-bucket",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storage_unit_id:** `str` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Bucket name. Lowercase letters, numbers, dots, and hyphens only; must start and end with a letter or number.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">get_keys_object_storage</a>(...) -> AccessKeyDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all access keys (access key and secret key pairs) for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.get_keys_object_storage(
    storage_unit_id="tenant$user",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storage_unit_id:** `str` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">get_cost_estimate_object_storage</a>() -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost of an object storage unit without creating one.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.get_cost_estimate_object_storage()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">set_user_quota_object_storage</a>(...) -> ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Sets the user quota limit for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.set_user_quota_object_storage(
    storage_unit_id="tenant$user",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storage_unit_id:** `str` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**max_size_gb:** `typing.Optional[float]` — Maximum total size for the storage unit, in gigabytes.
    
</dd>
</dl>

<dl>
<dd>

**remove_limit:** `typing.Optional[bool]` — When true, removes any existing storage limit instead of setting a value.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">delete_unit_object_storage</a>(...) -> ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes an object storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.delete_unit_object_storage(
    storage_unit_id="tenant$user",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storage_unit_id:** `str` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.object_storage.<a href="src/americancloud/object_storage/client.py">delete_bucket_object_storage</a>(...) -> ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a bucket from the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.object_storage.delete_bucket_object_storage(
    storage_unit_id="tenant$user",
    bucket_name="my-bucket",
    purge_objects=True,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storage_unit_id:** `str` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**bucket_name:** `str` — Bucket name
    
</dd>
</dl>

<dl>
<dd>

**purge_objects:** `typing.Optional[bool]` — Whether to purge objects in the bucket (default: true)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## ssh-keys
<details><summary><code>client.ssh_keys.<a href="src/americancloud/ssh_keys/client.py">list_ssh_keys</a>(...) -> ListSshKeysResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.ssh_keys.list_ssh_keys()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ssh_keys.<a href="src/americancloud/ssh_keys/client.py">create_ssh_keys</a>(...) -> CreateSshKeyResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

If publicKey is provided, registers your existing public key. If omitted, generates a new key pair and returns the private key (shown only once).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.ssh_keys.create_ssh_keys(
    name="my-ssh-key",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — Name of the SSH key pair
    
</dd>
</dl>

<dl>
<dd>

**public_key:** `typing.Optional[str]` — Public key to register. If provided, the key pair is registered using your existing key. If omitted, a new key pair is generated and the private key is returned.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ssh_keys.<a href="src/americancloud/ssh_keys/client.py">delete_ssh_keys</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.ssh_keys.delete_ssh_keys(
    name="my-ssh-key",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — Name of the SSH key pair to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## block-storage
<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">list_block_storage</a>(...) -> ListBlockStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns block storage volumes for the authenticated account. Optionally filter by virtual machine.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.list_block_storage()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**vm_id:** `typing.Optional[str]` — Filter volumes attached to a specific virtual machine
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">create_block_storage</a>(...) -> VolumeResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new block storage volume. To preview pricing without creating anything, use POST /storage/block-storage/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.create_block_storage(
    name="my-block-storage",
    size_gb=100,
    region="us-west-0",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateVolumeDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">get_block_storage</a>(...) -> VolumeResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns details of a specific block storage volume
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.get_block_storage(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">delete_block_storage</a>(...) -> VolumeDeletionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a block storage volume. This operation cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.delete_block_storage(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">get_cost_estimate_block_storage</a>(...) -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a volume with the given specs without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.get_cost_estimate_block_storage(
    name="my-block-storage",
    size_gb=100,
    region="us-west-0",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateVolumeDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">attach_block_storage</a>(...) -> VolumeOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Attaches a volume to a specified virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.attach_block_storage(
    id="123e4567-e89b-12d3-a456-426614174000",
    vm_id="f8d7e91c-f24d-4c21-b75e-4c7c5389c305",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**vm_id:** `str` — The ID of the virtual machine to attach the volume to
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">detach_block_storage</a>(...) -> VolumeOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Detaches a volume from its currently attached virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.detach_block_storage(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">resize_block_storage</a>(...) -> VolumeOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Increases the size of a block storage volume. The new size must be larger than the current size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.resize_block_storage(
    id="123e4567-e89b-12d3-a456-426614174000",
    size_gb=200,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**size_gb:** `int` — The new size of the volume in GB. Must be larger than the current size.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.block_storage.<a href="src/americancloud/block_storage/client.py">list_snapshots_block_storage</a>(...) -> ListSnapshotsBlockStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all snapshots for the specified volume.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.block_storage.list_snapshots_block_storage(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## snapshots
<details><summary><code>client.snapshots.<a href="src/americancloud/snapshots/client.py">list_snapshots</a>(...) -> ListSnapshotsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all snapshots for the authenticated account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.snapshots.list_snapshots()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.snapshots.<a href="src/americancloud/snapshots/client.py">create_snapshots</a>(...) -> SnapshotResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new snapshot from a block storage volume. To preview pricing without creating anything, use POST /storage/snapshots/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.snapshots.create_snapshots(
    volume_id="vol-123456",
    name="my-data-snapshot",
    type="DataDisk",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateSnapshotDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.snapshots.<a href="src/americancloud/snapshots/client.py">get_snapshots</a>(...) -> SnapshotResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns details of a specific snapshot
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.snapshots.get_snapshots(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Snapshot ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.snapshots.<a href="src/americancloud/snapshots/client.py">delete_snapshots</a>(...) -> SnapshotOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a snapshot. This operation cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.snapshots.delete_snapshots(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Snapshot ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.snapshots.<a href="src/americancloud/snapshots/client.py">get_cost_estimate_snapshots</a>(...) -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a snapshot of the given volume without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.snapshots.get_cost_estimate_snapshots(
    volume_id="vol-123456",
    name="my-data-snapshot",
    type="DataDisk",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateSnapshotDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.snapshots.<a href="src/americancloud/snapshots/client.py">revert_snapshots</a>(...) -> SnapshotOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reverts the volume associated with this snapshot to its point-in-time state.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.snapshots.revert_snapshots(
    id="123e4567-e89b-12d3-a456-426614174000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Snapshot ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## wordpress
<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">get_wordpress</a>() -> WordPressInstanceDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the active WordPress instance for the account. Returns 404 if the account has no WordPress instance.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.get_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">create_wordpress</a>(...) -> WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new WordPress hosting instance for the authenticated account. To preview pricing without creating anything, use POST /wordpress/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.create_wordpress(
    package_label="wordpress-10",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateWordPressDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">cancel_wordpress</a>() -> WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Cancels and removes the WordPress instance for the authenticated account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.cancel_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">get_cost_estimate_wordpress</a>(...) -> CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a WordPress instance on the given package without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.get_cost_estimate_wordpress(
    package_label="wordpress-10",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateWordPressDto` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">update_password_wordpress</a>(...) -> WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the password for the WordPress hosting account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.update_password_wordpress(
    new_password="newPassword",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**new_password:** `str` — New password for the WordPress hosting account
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">create_session_wordpress</a>() -> SessionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a login session URL for managing your WordPress hosting
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.create_session_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">get_quota_wordpress</a>() -> QuotaInfoDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns disk and resource quota information for the WordPress instance
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.get_quota_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">get_max_instances_wordpress</a>() -> MaxInstancesDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the maximum number of WordPress sites allowed for the current package
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.get_max_instances_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">list_websites_wordpress</a>() -> WebsitesDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a list of all WordPress websites/sites for the account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.list_websites_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">get_bandwidth_wordpress</a>() -> BandwidthDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns bandwidth usage statistics for the WordPress instance
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.get_bandwidth_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">get_nameservers_wordpress</a>() -> NameserversDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the nameserver addresses for the WordPress hosting server
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.get_nameservers_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">change_package_wordpress</a>(...) -> WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upgrades the WordPress instance to a higher tier package/plan
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.change_package_wordpress(
    package_label="wordpress-25",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**package_label:** `str` — New package label to upgrade to
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">list_packages_wordpress</a>(...) -> ListPackagesWordpressResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all available WordPress hosting packages/plans
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.list_packages_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">get_current_package_wordpress</a>() -> WordPressPackageDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the current package for the account's WordPress instance
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.get_current_package_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.wordpress.<a href="src/americancloud/wordpress/client.py">list_upgrade_packages_wordpress</a>(...) -> ListUpgradePackagesWordpressResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns packages available for upgrade (higher tier than current)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from americancloud import AmericancloudApi
from americancloud.environment import AmericancloudApiEnvironment

client = AmericancloudApi(
    api_key="<value>",
    api_client_secret="<X-API-Client-Secret>",
    environment=AmericancloudApiEnvironment.PRODUCTION,
)

client.wordpress.list_upgrade_packages_wordpress()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

